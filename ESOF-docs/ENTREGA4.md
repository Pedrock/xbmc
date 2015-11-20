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

Este, usa o [*buildbot Jenkins*](http://jenkins.kodi.tv/) para testar a build do projeto nas várias plataformas suportadas.

#### Controlabilidade

O *Kodi* contém classes especificas para os seus testes de *software*. Devido à complexidade da plataforma, cada classe de teste está encarregue por testar cada componente, facilitando e evidenciando a importancia da realização dos mesmos. Os testes relativos ao *Kodi* são realizados ao nivel da classe.

No que diz respeito à controlabilidade dos componentes sob teste (CUT - *Component Under Test*), ao analisarmos em melhor promenor as funções de teste, conseguimos constatar que é possivel, num dado instante, aceder às propriedades de um objecto, conseguindo asdeste modo ter um maior controlo sob o *software*, que permite uma maior automização e otimização dos testes. 

#### Observabilidade

(The degree to which it is possible to observe (intermediate and final) test results.)

#### Isolabilidade

(The degree to which the component under test (CUT) can be tested in isolation.)

#### Separação de Funcionalidades

(The degree to which the component under test has a single, well defined responsibility.)

#### Compreensibilidade

(The degree to which the component under test is documented or self-explaining.)

#### Heterogeneidade

(The degree to which the use of diverse technologies requires to use diverse test methods and tools in parallel.)

### Estatisticas de Teste

( Number of tests (# tests unitários; # tests de sistema, # tests de desempenho, ...)
     % coverage (given by tools like EclEmma)
     Code coverage: is it any good? (see http://avandeursen.com/2013/11/19/test-coverage-not-for-managers/) )
     
Atualmente, o *Kodi* conta com um total de 598 testes, sendo que estes se encontram repartidos por diferentes classes que representam as funcionalidades dos componentes que pretendemos testar, como podemos observar em [*Kodi* - *All Tests*](http://jenkins.kodi.tv/job/TestMulti-All/lastCompletedBuild/testReport/(root)). 

### Correção de um *Bug*

([Opcional] Take a bug report, create test cases to reproduce it, and fix it, eventually using automated software fault diagnosis techniques. (grade >18) )

### Análise Crítica
