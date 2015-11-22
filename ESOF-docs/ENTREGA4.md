# Relatório ESOF - 4

## *Kodi* - Verificação e Validação de Software

### Introdução

Neste relatório iremos analisar o *Kodi* relativamente à sua validação e verificação de *software*. 

O objectivo da validação e verificação de *software* é assegurar que este cumpre as necessidades dos diferentes *stakeholders*, como os utilizadores finais, os programadores e os gestores de projeto, ou seja, a confirmação de que este cumpre todos os seus requisitos. Enquanto que a verificação envolve a análise do sistema de modo a que este cumpra os seus requisitos funcionais, a validação engloba a confirmação de que o sistema atende às necessidades e expectativas do cliente.
Apesar destes dois processos serem diferentes, eles estão intimamente ligados e são bastante dependentes um do outro. 

A validação e verificação de *software* no *Kodi* é feita por *Quality Assurance Testers*. A equipa de segurança de qualidade é uma parte essencial do Kodi para garantir o contínuo sucesso do projecto. Esta é responsável por testar os produtos e investigar possíveis problemas que possam surgir durante este processo. [*Kodi* - *Assurance Testing*](http://kodi.wiki/view/HOW-TO:Help_with_quality_assurance_testing)

Primeiramente iremos abordar o grau de testabilidade do *software*, onde iremos analizar a **controlabilidade** do estado dos seus componentes, a **observabilidade** do resultado dos testes, a **isolabilidade** dos componentes, a **separação de funcionalidades do** ***software***, a **compreensibilidade** dos componentes e a **heterogeneidade** das plataformas usadas. Seguidamente iremos apresentar algumas **estatisticas de teste** referentes ao seu número e cobertura, e por final, iremos analisar e **corrigir um** ***bug***.

### Grau de Testabilidade do Software

O grau de testabilidade do software analisa o quão fácil é de testar os diferentes componentes deste. Devido à complexidade que o *Kodi* apresenta os testes de *software* são distribuidos pelos seus diferentes módulos e funcionalidades. Deste modo torna-se mais fácil gerir a qualidade destes. 

#### Controlabilidade

A controlabilidade de um *software* define o grau de controlo do estado dos componentes a serem testados. 

O *Kodi* contém classes especificas para os seus testes de *software*. Devido à complexidade da plataforma, cada classe de teste está encarregue por testar cada componente, facilitando e evidenciando a importância da realização dos mesmos. Os testes relativos ao *Kodi* são realizados ao nivel da classe.

No que diz respeito à controlabilidade dos componentes sob teste (CUT - *Component Under Test*), ao analisarmos em melhor promenor as funções de teste, conseguimos constatar que é possivel, num dado instante, aceder às propriedades de um objecto, conseguindo deste modo ter um maior controlo sob o *software*, que por sua vez, permite uma maior automização e otimização dos testes. 

#### Observabilidade

O *Kodi* utiliza usa o [*buildbot Jenkins*](http://jenkins.kodi.tv/) como ferramenta de testes unitários para testar tanto a build do projeto como os seus *pull requests*, nas várias plataformas suportadas. Este *buildbot*, como dito no [Relatório 2](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/ENTREGA2.md), é o sucessor do [*buildbot Billy*](http://kodi.tv/jenkins-servers-and-mirrrors/). O *Jenkins* tem como vantagem conferir uma maior versatilidadee e permitir testar o código de um *pull request* antes de ocorrer o *merge*.

Assim, a partir da [página de testes](http://jenkins.kodi.tv/view/All/job/TestMulti-All/lastCompletedBuild/testReport/(root)) do *media center* podemos ver o número total de testes e a sua distribuição numérica por ficheiro/classe de testes. Por cada classe temos ainda o número de testes que falharam, aqueles que foram saltados, os que passaram e a duração do tempo de execução de todos os seus testes no geral e também individualmente. Um dos possivies exemplos é a classe [*TestFileUtils*](http://jenkins.kodi.tv/view/All/job/TestMulti-All/lastCompletedBuild/testReport/(root)/TestFileUtils/) que tem duas funções de teste, cada uma com tempo de duração diferente. Para além do tempo de duração, cada caso de teste apresenta informação acerca do histórico do resultado desse teste (duração e resultado), como é possivel ver num dos casos de teste da classe referida anteriormente, a função [*DeleteItemString*](http://jenkins.kodi.tv/view/All/job/TestMulti-All/lastCompletedBuild/testReport/(root)/TestFileUtils/DeleteItemString/history/).

Para além do descrito no parágrafo anterior, é ainda possivel observar no *output* dos resultados dos testes na consola, para cada [plataforma](http://jenkins.kodi.tv/job/TestMulti-All/), várias informações acerca dos mesmos. Como é o caso do [*Windows*](http://jenkins.kodi.tv/job/WIN-32/6752/console), nos resultados do último *build* de testes passaram 475 dos 476 testes existentes na altura.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/resultado_WIN-32.JPG)

Para além de toda a informação referida anteriormente, aquando de algum erro podemos ver os detalhes e o *Stack Trace* do mesmo, como é exemplo o [erro referido no parágrafo anterior](http://jenkins.kodi.tv/job/WIN-32/6752/testReport/).

Visto isto, concluímos que a observabilidade nos diferentes componentes do *Kodi* é bastante boa, facultando a informação necessária para a localização e resolução do erro.

#### Isolabilidade

Devido à complexidade que o *Kodi* apresenta, a maior parte das classes dos diferentes pacotes faz uso de outras classes e métodos pertencentes a outros pacotes. Estando estas intimamente ligadas e interdependentes. Assim, ao testarmos um componente de um determinado módulo, estamos também a testar, indiretamente, outros componentes de diferentes módulos. 

No entanto, existem casos em que a isolabilidade dos módulos testados é melhorada por [objectos *mocks*](https://pt.wikipedia.org/wiki/Objeto_Mock), que basicamente são "falsos" objectos que simulam o comportamento de uma classe ou objeto “real” para que possamos focar o teste no componente a ser testado. Um exemplo do uso de objectos *mocks* é a classe [gtest-spi.h](https://github.com/Pedrock/xbmc/blob/master/lib/gtest/include/gtest/gtest-spi.h), que tem como objectivo testar a ferramente de teste.

Deste modo, concluímos que o *Kodi* tem um baixo grau de isolabilidade na maior parte dos módulos que fazem uso de componentes de outros módulos, pois o sucesso de um teste a um determinado módulo depende não só das funções que estão a ser diretamente testadas, mas também do sucesso das funções utilizadas por essa função, pertencentes a outros módulos. Como a maior parte dos testes de *software* do *Kodi* são referentes a módulos mais abrangentes e por isso também de maior importância, podemos considerar que, no geral, o *Kodi* tem um baixo grau de isolabilidade.


#### Separação de Responsabilidades

No *Kodi*, a divisão de responsabilidades entre os seus diferentes componentes é uma parte bastante importante de todo o seu *software*. Devido à grande extensão da plataforma, é essencial garantir que existe uma correcta e distinta divisão de funcionalidades entre os seus diferentes módulos, de modo a que o código não se torne cada vez mais confuso e, por conseguinte, menos testável.

Atualmente, os testes de *software* do *media center* encontram-se divididos em 92 módulos (representados por classes). Cada um destes módulos tem como objecto de teste várias funcionalidades e várias sub-funcionalidades pertencentes à mesma, como é exemplo o pacote [*network*](https://github.com/Pedrock/xbmc/tree/master/xbmc/network), em que as suas funcionalidades são testadas pela classe de testes [TestWebServer.cpp](http://jenkins.kodi.tv/job/TestMulti-All/lastCompletedBuild/testReport/(root)/TestWebServer/). O pacote *network* disponibiliza a ligação em rede e à internet, sendo repartido em várias sub-funcionalidades, as quais são testadas pelas múltiplas funções de teste pertencentes à classe [TestWebServer.cpp](https://github.com/Pedrock/xbmc/blob/master/xbmc/network/test/TestWebServer.cpp).

Assim, podemos concluir que o *Kodi* apresenta uma repartição de funcionalidades bem definida, o que permite um maior grau de isolabilidade de testes e o aumento de eficácia destes.


#### Compreensibilidade

O grau de compreensibilidade de um software pode ter um forte impacto no seu desenvolvimento e manutenção. Para avaliar um determinado projeto, são definidas métricas que permitem registar a qualidade do código, quanto à sua facilidade de interpretação. Nesta secção, avaliaremos o *Kodi* segundo os padrões estabelecidos por essas métricas de compreensibilidade de software.

Começando pela percentagem de comentários em código, o *Kodi* não é o melhor exemplo, revelando uma falha considerável neste ponto e levando a que novos colaboradores percam mais tempo na análise do projeto. Contudo, esta falta de comentários ao código é compensada pelo recurso a funções de métrica reduzida (com reduzido número médio de linhas) e a utilização de nomes intuitivos para variáveis e funções, tornando o código mais descritivo e facilitando a sua interpretação. Relativamente à complexidade dos algoritmos utilizados, em geral, não são implementadas operações de cálculo exigente ou complexo, o que melhora a compreensibilidade do projeto.

Desta forma, concluimos que, no que toca à Compreensibilidade, o *Kodi* apresenta resultados satisfatórios, dado que a presença da documentação apropriada do código facilitaria significativamente a contribuição de qualquer colaborador para o projeto.

#### Heterogeneidade

Com a crescente expansão de um projecto e o uso de novas tecnologias cresce também a necessidade de métodos de teste diversificados de modo a que estes consigam abranger as diversas tecnologias utilizadas.

O *Kodi*, devido ao número de funcionalidades e tecnologias implementadas é bastante complexo, apresentando assim uma grande heterogeneidade. As informações relativas às dependencias utilizadas, consoante a plataforma em uso, encontram-se listadas na pasta [docs](https://github.com/Pedrock/xbmc/tree/master/docs) do projecto.

Como podemos constatar a partir dos ficheiros referenciados acima, o *Kodi* utiliza várias tecnologias externas que lhe permitem compilar o projeto. As principais bibliotecas e tecnologias utilizadas para o efeito são:
* [Cmake](https://cmake.org/) - sistema multiplataforma de geração automática (arquivos do tipo *makefile*).
* [NSIS](http://nsis.sourceforge.net/Main_Page) - sistema *open source* que permite criar instaladores do *Windows*.
* [Buildbot Jenkins](http://jenkins.kodi.tv/) - Bot que permite compilar e testar código.

Para além destas, são também utilizadas outras tecnologias responsáveis pela parte *multimédia* do *Kodi*, das quais são exemplo:
* libmpcdec-dev
* libmpeg2-4-dev
* libjasper-dev
* libjpeg-dev 


Devido à sua multiplicidade, este deveria apresentar uma elevada *coverage* de testes nas suas diferentes tecnologias, de modo a suportar uma correcta implementação em todas, o que não é o caso, como podemos observar no tópico seguinte.

No *core* do projeto, são usados motores de áudio, *video renderers* e bibliotecas que atuam sobre DVD´s que não se encontram devidamente testadas. Com isto, o *Kodi* pode sofrer retrocessos na implementação de novas funcionalidades, porque nao havendo testes nestas zonas, facilmente se podem gerar *bugs* que não são facilmente observáveis durante a execução do programa. Deste modo, o custo de esforço e tempo para uma posterior resolução pode aumentar exponencialmente.

Visto isto, o *bot* de compilação que o *Kodi* utiliza é de extrema importância para o projeto. Como já dito anteriormente, este *bot* permite verificar a compilação do código de um *pull request* antes da realização de um *merge*. Assim, permite que o código do *Kodi* não fique incompilável.


### Estatisticas de Teste
     
Atualmente, o *Kodi* conta com um total de 598 testes unitários, sendo que estes se encontram repartidos por diferentes classes que representam as funcionalidades dos componentes que pretendemos testar, como podemos observar em [*Kodi* - *All Tests*](http://jenkins.kodi.tv/job/TestMulti-All/lastCompletedBuild/testReport/(root)). Ao analisarmos o [histórico de testes do *Kodi*](http://jenkins.kodi.tv/job/TestMulti-All/lastCompletedBuild/testReport/(root)/history/), observamos que o número de testes de *software* diminuiu acentuadamente, e com isto também a duração de execução de todos os testes. Nos gráficos a seguir podemos observar o histórico da duração e do número total de testes de *software* do *Kodi*, respetivamente.

![Historico duração dos testes](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/dura%C3%A7%C3%A3o-hist%C3%B3rico-testes.JPG)

![Historico número de testes](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/numero-total-testes-historico.JPG)

Para uma posterior análise de cobertura de testes, compilámos o *Kodi* no ubuntu, seguindo as [intruções de instalação](https://github.com/xbmc/xbmc/blob/master/docs/README.ubuntu). Para obtermos os relatório das linhas de código de cobertura dos testes compilámos o código com as seguintes flags:
- -ftest-coverage
- -fprofile-arcs

Seguidamente corremos os testes que, por sua vez geraram vários ficheiros de cobertura por ficheiro. Para processar esses vários ficheiros e agrupá-los num só utilizámos a extenção [lcov](http://ltp.sourceforge.net/coverage/lcov.php) e por último, usámos o [genhtml](http://linux.die.net/man/1/genhtml) para criar vários ficheiros html a partir desse ficheiro de forma a tornar os dados facilmente legíveis.

Os resultados obtidos foram os seguintes:

![*Coverage* - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/coverage.png)

A partir da imagem, podemos concluir que o *Kodi* apresenta uma má cobertura de testes, tendo apenas 4.1 % de cobertura de linhas e 8.8 % de cobertura de funções, no geral. O ficheiro que apresenta a maior cobertura de testes é o [xbmc/filesystem/test](https://github.com/Pedrock/xbmc/tree/master/xbmc/filesystem/test) com 100% de cobertura de linhas, podendo dizer-se que é uma "exceção à regra" relativamente à percentagem de cobertura dos restantes ficheiros. Isto torna-se compreensivel por ser um ficheiro que está encarregue por testar as funções do pacote *filesystem*, responsável por fornecer as funcionalidades do sistema de arquivos de ficheiros, controlando o armazenamento e os respetivos dados.

Apesar do *Kodi* apresentar uma cobertura de testes bastante baixa, existem funcionalidades que não são possiveis testar, como por exemplo a sua *interface* gráfica. O que poderá, de certa forma, atenuar um pouco a sua falta de cobertura.


### Correção de um *Bug*

([Opcional] Take a bug report, create test cases to reproduce it, and fix it, eventually using automated software fault diagnosis techniques. (grade >18) )

### Análise Crítica

Após a detalhada análise ao *Kodi* presente neste relatório, podemos afirmar que as componentes de validação e verificação não foram geridas apropriadamente ao longo do seu desenvolvimento.

Apresentando um grau de isolabilidade relativamente reduzido, uma percentagem de cobertura de testes insatisfatória e uma pobre quantidade de documentação do código, inviabiliza-se o potencial da fácil implementação de novas funcionalidades que a equipa do *Kodi* teve na estruturação do código, como analisada no [relatório anterior](https://github.com/Pedrock/xbmc/ESOF-docs/ENTREGA3.md). Por estes motivos, torna-se significativamente complicada a análise e correção de bugs no projeto, sendo necessárias diversas horas de investigação e adaptação ao respetivo código.

Destaca-se, no entanto, a adoção de tecnologias de teste como o **BuildBot Jenkins** que permitem alguma robustez na validação e verificação do produto, no momento de submissão de melhorias introduzidas pelos colaboradores.