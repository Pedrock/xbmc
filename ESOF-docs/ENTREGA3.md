# Relatório ESOF - 3

## *Kodi* - Arquitetura 4+1

### Vista Lógica 
A perspetiva lógica é orientada para a funcionalidade que o sistema fornece aos utilizadores.


### *Perspetiva de Implementação*


Nesta abordagem, o objetivo será a representação e ilustração do projeto segundo uma perspetiva do programador, tendo  como finalidade a supervisão do software desenvolvido.

Recorre-se, portanto, a Diagramas UML de Componentes, usados para ilustrar estruturas de sistemas complexos, demonstrando a forma como diferentes componentes do projeto se encontram interligados.

O diagrama que se segue, demonstra de forma simplificada, os componentes constituintes do projeto, mas com a informação indispensável para apresentar a forma como estes interagem entre si, dando uma perspetiva ao programador e utilizador sobre a estrutura do produto.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/development_view.png)

Analisando o diagrama, conclui-se que, de facto, a estruturação do projeto é uma prioridade da equipa do *Kodi*. Desta forma, a possibilidade de reformulação do código e adição de novas funcionalidades torna-se menos problemática.



**_"Kodi should still compile and run if a non-essential module/library is disabled or removed.”_**

Um dos princípios do *Kodi* baseia-se na utilização de módulos de software independentes. A introdução de módulos de tal forma adaptados, permite uma melhor organização e manutenção do código. Desta forma, mesmo que um módulo apresente falhas de compilação, o projeto é capaz de executar com as restantes funcionalidades que não o utilizem. Estes módulos podem ser encarados como blocos que interagem entre si, embora distinguindo-s pelas atividades que lhes são atribuidas. Por sua vez, estes blocos são organizados em grupos funcionais independentes.

Seguidamente apresenta-se uma perspetiva deste design modular do *Kodi*:

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/modular_design.png)

Como se pode observar, os blocos modulares dividem a arquitetura do projeto segundo uma perspetiva vertical. Desta forma, demonstra-se a independência dos diferentes blocos, segundo camadas minuciosamente estruturadas. Este modelo de organização do software previne, por exemplo, a redefinição de uma função múltiplas vezes. Uma outra vantagem será, também, a incrivel evolução na eficiência de desenvolvimento do programa, uma vez que os módulos bem estabelecidos e diferenciados permitem uma fácil manutenção do código e implementação de novas funcionalidades.

### Vista de Processo


### Vista de *Deployment* 

A vista de *deployment* têm como objectivo representar a relação entre as componentes de software e hardware do sistema. Possibilitando assim, mostrar de que modo os artefactos de um sistema são distribuídos em nós de hardware.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/deployment-view.png)

Como podemos ver a partir do diagrama anterior, o utilizador, a partir do *Kodi*, acede ao repositorio oficial de *addons* deste para procurar atualizações para os *addons* que o utilizador tem instalado, ou para instalar novos. O utilizador pode também aceder através de um *browser* ao *website* oficial para fazer download de uma das compilações do programa, as quais se encontram na base de dados do *Kodi*. Estas são compiladas pelas máquinas com o [*buildbot* Jenkins](http://jenkins.kodi.tv/).

### Vista de Casos de Uso

Esta vista relaciona todas as outras vistas, anteriormente descritas, do modelo 4+1. É aqui que podemos observar as sequências de interações entre os objectos(neste caso o utilizador) e os diferentes processos.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/use-case-diagram.png)


