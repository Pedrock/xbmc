# Relatório ESOF - 4

## *Kodi* - Verificação e Validação de Software

### Introdução

Neste relatório iremos analisar o *Kodi* relativamente à sua validação e verificação de *software*. 

O objectivo da validação e verificação de *software* é assegurar que este cumpre as necessidades dos diferentes *stakeholders*, como os utilizadores finais, os programadores e os gestores de projeto, ou seja, a confirmação de que este cumpre todos os seus requisitos. Enquanto que a verificação envolve a análise do sistema de modo a que este cumpra os seus requisitos funcionais, a validação engloba a confirmação de que o sistema atende as necessidades e expectativas do cliente.
Apesar destes dois processos serem diferentes, eles estão intimamente ligados e são bastante dependentes um do outro. 

A validação e verificação de *software* no *Kodi* é feita por *Quality Assurance Testers*. A equipa de segurança de qualidade é uma parte essencial do Kodi para garantir o contínuo sucesso do projecto. Esta é responsável por testar os produtos e investigar possíveis problemas que possam surgir durante este processo. [*Kodi* - *Assurance Testing*](http://kodi.wiki/view/HOW-TO:Help_with_quality_assurance_testing)

Primeiramente iremos abordar o grau de testabilidade do *software*, onde iremos analizar a controlabilidade do estado dos seus componentes, a observabilidade do resultado dos testes, a isolabilidade dos componentes, a separeação de funcionalidades do *software*, a compreensibilidade dos componentes e a heterogeneidade das plataformas usadas. Seguidamente iremos apresentar algumas estatisticas de teste referentes ao seu número e cobertura, e por final, iremos analisar e corrigir um *bug*.

### Grau de Testabilidade do Software

O grau de testabilidade do software analisa o quão fácil é de testar os diferentes componentes deste. Devido à complexidade que o *Kodi* apresenta os testes de software são distribuidos pelos seus diferentes módulos. Deste modo torna-se mais fácil gerir a qualidade destes. 

#### Controlabilidade

(The degree to which it is possible to control the state of the component under test (CUT) as required for testing.)

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

### Correção de um *Bug*

([Opcional] Take a bug report, create test cases to reproduce it, and fix it, eventually using automated software fault diagnosis techniques. (grade >18) )

### Análise Crítica
