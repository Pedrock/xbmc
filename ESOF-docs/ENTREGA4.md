# Relatório ESOF - 4

## *Kodi* - Verificação e Validação de Software

### Introdução

Neste relatório iremos analisar o *Kodi* relativamente à sua validação e verificação de *software*. 

O objectivo da validação e verificação de *software* é assegurar que este cumpre as necessidades dos diferentes *stakeholders*, como os utilizadores finais, os programadores e os gestores de projeto, ou seja, a confirmação de que este cumpre todos os seus requisitos. Enquanto que a verificação envolve a análise do sistema de modo a que este cumpra os seus requisitos funcionais, a validação engloba a confirmação de que o sistema atende as necessidades e expectativas do cliente.
Apesar destes dois processos serem diferentes, eles estão intimamente ligados e são bastante dependentes um do outro. 

A validação e verificação de *software* no *Kodi* é feita por *Quality Assurance Testers*. A equipa de segurança de qualidade é uma parte essencial do Kodi para garantir o contínuo sucesso do projecto. Esta é responsável por testar os produtos e investigar possíveis problemas que possam surgir durante este processo. [*Kodi* - *Assurance Testing*](http://kodi.wiki/view/HOW-TO:Help_with_quality_assurance_testing)

Primeiramente iremos abordar o grau de testabilidade do *software*, onde iremos analizar a controlabilidade do estado dos seus componentes, a observabilidade do resultado dos testes, a isolabilidade dos componentes, a separeação de funcionalidades do *software*, a compreensibilidade dos componentes e a heterogeneidade das plataformas usadas. Seguidamente iremos apresentar algumas estatisticas de teste referentes ao seu número e cobertura, e por final, iremos analisar e corrigir um *bug*.

### Grau de Testabilidade do Software

O grau de testabilidade do software analisa o quão fácil é de testar os diferentes componentes deste. Devido à complexidade que o *Kodi* apresenta os testes de *software* são distribuidos pelos seus diferentes módulos e pelas suas funcionalidades. Deste modo torna-se mais fácil gerir a qualidade destes. 

#### Controlabilidade

O *Kodi* contém classes especificas para os seus testes de *software*. Devido à complexidade da plataforma, cada classe de teste está encarregue por testar cada componente, facilitando e evidenciando a importancia da realização dos mesmos. Os testes relativos ao *Kodi* são realizados ao nivel da classe.

No que diz respeito à controlabilidade dos componentes sob teste (CUT - *Component Under Test*), ao analisarmos em melhor promenor as funções de teste, conseguimos constatar que é possivel, num dado instante, aceder às propriedades de um objecto, conseguindo deste modo ter um maior controlo sob o *software*, que permite uma maior automização e otimização dos testes. 

#### Observabilidade

O *Kodi* utiliza usa o [*buildbot Jenkins*](http://jenkins.kodi.tv/) como ferramenta de testes unitários para testar tanto a build do projeto como os seus *pull requests*, nas várias plataformas suportadas. Este *buildbot*, como dito no [Relatório 2](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/ENTREGA2.md), é o sucessor do [*buildbot Billy*](http://kodi.tv/jenkins-servers-and-mirrrors/). O *Jenkins* tem como vantagem conferir uma maior versatilidadee e permitir testar o código de um *pull request* antes de ocorrer o *merge*.

Assim, a partir da [página de testes](http://jenkins.kodi.tv/view/All/job/TestMulti-All/lastCompletedBuild/testReport/(root)) do *media center* podemos ver o número total de testes e a sua distribuição numérica por ficheiro/classe de testes. Por cada classe temos ainda o número de testes que falharam, aqueles que foram saltados, os que passaram e a duração do tempo de execução de todos os seus testes no geral e também individualmente. Um dos possivies exemplos é a classe [*TestFileUtils*](http://jenkins.kodi.tv/view/All/job/TestMulti-All/lastCompletedBuild/testReport/(root)/TestFileUtils/) que tem duas funções de teste, cada uma com tempo de duração diferente. Para além do tempo de duração, cada caso de teste apresenta informação acerca do histórico do resultado desse teste (duração e resultado), como é possivel ver num dos casos de teste da classe referida anteriormente, a função [*DeleteItemString*](http://jenkins.kodi.tv/view/All/job/TestMulti-All/lastCompletedBuild/testReport/(root)/TestFileUtils/DeleteItemString/history/).

Para além do descrito no parágrafo anterior, é ainda possivel observar no *output* dos resultados dos testes na consola, para cada [plataforma](http://jenkins.kodi.tv/job/TestMulti-All/), várias informações acerca dos mesmos. Como é o caso do [*Windows*](http://jenkins.kodi.tv/job/WIN-32/6752/console), em nos resultados do último *build* de testes passaram 475 dos 476 testes existentes na altura.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/resultado_WIN-32.JPG)

Para além de toda a informação referida anteriormene, aquando de algum erro podemos ver os detalhes e o *Stack Trace* do mesmo, como é o exemplo o [erro referido no parágrafo anterior](http://jenkins.kodi.tv/job/WIN-32/6752/testReport/).

Visto isto, concluímos que a observabilidade nos diferentes componentes do *Kodi* é bastante boa, facultando a informação necessária para a localização e resolução do erro.

#### Isolabilidade

Devido à complexidade que o *Kodi* apresenta, a maior parte das classes dos diferentes pacotes faz uso de outras classes e métodos pertencentes a outros pacotes. Estando estas intimamente ligadas e interdependentes, ao testarmos um componente de um determinado módulo, estamos também a testar, indiretamente, outros componentes de diferentes módulos. 

No entanto, existem casos em que a isolabilidade dos módulos testados é melhorada por [objectos *mocks*](https://pt.wikipedia.org/wiki/Objeto_Mock), que basicamente são "falsos" objectos que simulam o comportamento de uma classe ou objeto “real” para que possamos focar o teste no componente a ser testado. Um exemplo do uso de objectos *mocks* é a classe [gtest-spi.h](https://github.com/Pedrock/xbmc/blob/master/lib/gtest/include/gtest/gtest-spi.h), que tem como objectivo testar a ferramente de teste.

Assim, concluímos que o *Kodi* tem assim um baixo grau de isolabilidade na maior parte dos módulos que fazem uso de componentes de outros módulos, pois o sucesso de um teste a um determinado módulo depende não só das funções que estão a ser diretamente testadas, mas também do sucessos das funções utilizadas por essa função, pertencentes a outros módulos. Como a maior parte dos testes de *software* do *Kodi* são referentes a módulos mais abrangentes e por isso também de maior importância, podemos considerar que, no geral, o *Kodi* tem um baixo grau de isolabilidade.


#### Separação de Responsabilidades

No *Kodi*, a divisão de responsabilidades entre os seus diferentes componentes é uma parte bastante importante de todo o seu *software*. Devido à grande extensão da plataforma, é essencial garantir que existe uma correcta e distinta divisão de funcionalidades entre os seus diferentes módulos, de modo a que o código não se torne cada vez mais confuso e, por conseguinte, menos testável.

Atualmente, os testes de *software* do *media center* encontram-se divididos em 92 módulos(representados por classes). Cada um destes módulos tem como objecto de teste várias funcionalidades, e várias sub-funcionalidades pertencentes à mesma, como é exemplo o pacote [*network*](https://github.com/Pedrock/xbmc/tree/master/xbmc/network), em que as suas funcionalidades são testadas pela classe de testes [TestWebServer.cpp](http://jenkins.kodi.tv/job/TestMulti-All/lastCompletedBuild/testReport/(root)/TestWebServer/). O pacote *network* disponibiliza a ligação em rede e à internet, sendo repartido em várias sub-funcionalidades, as quais são testadas pelas múltiplas funções de teste pertencentes à classe [TestWebServer.cpp](https://github.com/Pedrock/xbmc/blob/master/xbmc/network/test/TestWebServer.cpp).

Assim, podemos concluir que o *Kodi* apresenta uma repartição de funcionalidades bem definida, o que permite um maior grau de isolabilidade de testes, assim como o aumento de eficácia destes.


#### Compreensibilidade

(The degree to which the component under test is documented or self-explaining.)

#### Heterogeneidade

(The degree to which the use of diverse technologies requires to use diverse test methods and tools in parallel.)

### Estatisticas de Teste

( Number of tests (# tests unitários; # tests de sistema, # tests de desempenho, ...)
     % coverage (given by tools like EclEmma)
     Code coverage: is it any good? (see http://avandeursen.com/2013/11/19/test-coverage-not-for-managers/) )
     
Atualmente, o *Kodi* conta com um total de 598 testes, sendo que estes se encontram repartidos por diferentes classes que representam as funcionalidades dos componentes que pretendemos testar, como podemos observar em [*Kodi* - *All Tests*](http://jenkins.kodi.tv/job/TestMulti-All/lastCompletedBuild/testReport/(root)). 

![*Coverage* - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/coverage.png)

### Correção de um *Bug*

([Opcional] Take a bug report, create test cases to reproduce it, and fix it, eventually using automated software fault diagnosis techniques. (grade >18) )

### Análise Crítica
