# Relatório ESOF - 3

## *Kodi* - Arquitetura 4+1

### Vista Lógica 
A perspetiva lógica é orientada para a funcionalidade que o sistema fornece aos utilizadores.


### Vista de Implementação

Nesta abordagem, o objetivo será a representação e ilustração do projeto segundo uma perspetiva do programador, tendo  como finalidade a supervisão do software desenvolvido.

Recorre-se, portanto, a Diagramas UML de Componentes, usados para ilustrar estruturas de sistemas complexos, demonstrando a forma como diferentes componentes do projeto se encontram interligados.

(...)

### Vista de Processo


### Vista de *Deployment* 

A vista de *deployment* têm como objectivo representar a relação entre as componentes de software e hardware do sistema. Possibilitando assim, mostrar de que modo os artefactos de um sistema são distribuídos em nós de hardware.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/deployment-view.png)

Como podemos ver a partir do diagrama anterior, o utilizador, a partir do *Kodi*, acede ao repositorio oficial de *addons* deste para procurar atualizações para os *addons* que o utilizador tem instalado, ou para instalar novos. O utilizador pode também aceder através de um *browser* ao *website* oficial para fazer download de uma das compilações do programa, as quais se encontram na base de dados do *Kodi*. Estas são compiladas pelas máquinas com o [*buildbot* Jenkins](http://jenkins.kodi.tv/).

### Vista de Casos de Uso

Esta vista relaciona todas as outras vistas, anteriormente descritas, do modelo 4+1. É aqui que podemos observar as sequências de interações entre os objectos(neste caso o utilizador) e os diferentes processos.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/use-case-diagram.png)


