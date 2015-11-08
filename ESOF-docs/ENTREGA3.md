# Relatório ESOF - 3

## *Kodi* - Arquitetura de Software

Um dos modelos usados para organizar as diferentes vistas arquitecturais em engenharia de *software* é o modelo de arquitetura 4+1. Este organiza a descrição da arquitectura de software em 5 vistas concorrentes. Cada vista trata um conjunto de objectivos específicos do projecto, de acordo com os diferentes *stakeholders*, como os utilizadores, utilizadores finais, programadores e gestores de projeto.
As vistas propostas pelo modelo são: a **vista lógia**, a **vista de implementação**, a **vista do processo**, a **vista de** **_deployment_** e a **vista de casos de uso**. Esta última serve para ilustrar e validar as demais.


### Vista Lógica 
O seguinte diagrama de *packages* descreve as depêndencias entre os principais componentes do código, caracterizando a vista lógica referente ao projeto em estudo. 

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/logical-view.png)

Devido à complexidade do *Kodi*, no diagrama acima foram apenas colocados os pacotes de maior relevância, tendo sido ainda alguns agrupados.
Como a maior parte do código se encontra em c++, linguagem na qual não existem *packages*, guiámo-nos pelos includes das classes e interpretámos como pacotes as pastas onde se encontravam as classes.

Assim, organizámos o *Kodi* em 9 pacotes. São eles:
  - **_Addons_** - Disponibiliza a API para os *addons* do *Kodi*.
  - **_Utils_** - Representa as funcionalidades auxiliares utilizadas, que são comuns aos restantes pacotes.
  - **_GUI_** - Constitui a interface para o utilizador e implementa os textos que acompanham as imagens e videos. Neste pacote foram incluidos os pacotes "guiinfo", "guilib", "interfaces" e "dialogs".
  - **_Input_** - Trata dos *inputs* do utilizador.
  - **_Network_** - Diponibiliza a ligação em rede e à internet.
  - **_Cores_** - Representa visualização de videos, imagens e programas, assim como a repodução de áudio. Este pacote é constituído pelos pacotes "music", "video", "pictures" e "media".
  - **_FileSystem_** - Fornece as funcionalidades do sistema de arquivos de ficheiros, controlando o armazenamento e os respetivos dados.
  - **_Playlists_** - Representa as sequências de músicas criadas pelo utilizador.
  - **_Peripherals_** - Fornece as funções de comunicação com os periféricos do computador.

### Vista de Implementação


Nesta abordagem, o objetivo será a representação e ilustração do projeto segundo uma perspetiva do programador, tendo como finalidade a supervisão do software desenvolvido.

Recorre-se, portanto, a Diagramas UML de Componentes, usados para ilustrar estruturas de sistemas complexos, demonstrando a forma como diferentes componentes do projeto se encontram interligados.

O diagrama que se segue demonstra de forma simplificada os componentes constituintes do projeto, mas com a informação indispensável para apresentar a forma como estes interagem entre si, dando uma perspetiva ao programador e utilizador sobre a estrutura do produto.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/development_view.png)

Analisando o diagrama conclui-se que, de facto, a estruturação do projeto é uma prioridade da equipa do *Kodi*. Desta forma, a possibilidade de reformulação do código e adição de novas funcionalidades tornam-se menos problemáticas.



**_"Kodi should still compile and run if a non-essential module/library is disabled or removed.”_**

Um dos princípios do *Kodi* baseia-se na utilização de módulos de software independentes. A introdução de módulos de tal forma adaptados, permite uma melhor organização e manutenção do código. Desta forma, mesmo que um módulo apresente falhas de compilação, o projeto é capaz de executar com as restantes funcionalidades que não o utilizem. Estes módulos podem ser encarados como blocos que interagem entre si, embora distinguindo-se pelas atividades que lhes são atribuidas. Por sua vez, estes blocos são organizados em grupos funcionais independentes.

Seguidamente, apresenta-se uma perspetiva deste design modular do *Kodi*:

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/modular_design.png)

Os blocos modulares dividem a arquitetura do projeto segundo uma perspetiva vertical. Desta forma, demonstra-se a independência dos diferentes blocos, segundo camadas minuciosamente estruturadas. Este modelo de organização do software previne, por exemplo, que uma função seja redefinida múltiplas vezes. Uma outra vantagem será, também, a incrivel evolução na eficiência de desenvolvimento do programa, uma vez que os módulos bem estabelecidos e diferenciados permitem uma fácil manutenção do código e implementação de novas funcionalidades.

### Vista de Processo


A vista de processo tem por objetivo demonstrar como é que o sistema é composto e interage entre os processos em tempo real. Para isso recorremos a um diagrama de atividades para assim ser mais fácil observar o fluxo de dados e de controlo de uma determinada atividade para outra  ao longo da sua execução.
![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/process-view.png)

Neste diagrama de atividades pode observar-se o comportamento do Kodi durante a sua execução por um utilizador.

Quando este pretende ouvir uma musica, ver um vídeo, ou uma imagem, é feito uma query à base de dados. Esta query vai retornar uma lista dos conteúdos disponíveis e a partir daí o utilizador vai selecionar o que desejar. Este pode também remover ou adicionar elementos à base de dados, a partir da interface intuitiva do Kodi. 

O utilizador pode também gerir os conteúdos dos addons inerentes à sua aplicação, podendo adicionar e remove-los. Para isto faz uma ligação aos repositórios instalados, de modo a saber que conteúdos pode adicionar e assim fazer download do que pretende. Ao consultar conteúdos externos ao Kodi, como a programação de TV ou a meteorologia, a aplicação faz uma ligação aos serviços que o addon implementa. Desta forma o utilizador consegue obter a informação e os conteúdos que pretende. 


### Vista de *Deployment* 

A vista de *deployment* têm como objectivo representar a relação entre as componentes de software e hardware do sistema, possibilitando assim mostrar de que modo os artefactos de um sistema são distribuídos em nós de hardware.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/deployment-view.png)

Como podemos ver a partir do diagrama de *deployment* anterior, o utilizador, a partir do *Kodi*, acede ao repositório oficial de *addons* para procurar atualizações para os *addons* que o utilizador tem instalado, ou para instalar novos. O utilizador pode também aceder através de um *browser* ao *website* oficial para fazer download de uma das compilações do programa, as quais se encontram na base de dados do *Kodi*. Estas são compiladas pelas máquinas com o [*buildbot* Jenkins](http://jenkins.kodi.tv/).

### Vista de Casos de Uso

Esta vista relaciona todas as outras anteriormente descritas. É aqui que podemos observar as sequências de interações entre os objectos (neste caso o utilizador) e os diferentes processos.

![Kodi - Image](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/use-case-diagram.png)


O *Kodi* permite aos utilizadores ver filmes, música e fotografias através da sua interface elegante e fácil de usar, desde que estes se encontrem adicionados às respetivas bibliotecas do utilizador. É um *media center* que tem como objetivo ser utilizado numa televisão na sala de estar, desempenhando o papel de uma *box* para a TV. Além disto, a plataforma possibilita a configuração do software, o que permite ao utilizador escolher, por exemplo, o tema que mais gostar, adicionar novos *addons* e *plug-ins*, que lhe permitam adicionar novas funcionalidades ao programa. Tais funcionalidades incluem ver a meteorologia, ir buscar *media* a sites externos, como ao Youtube, por exemplo, ver TV online e muito mais. Estes *addons* são atualizados automaticamente pelo programa pelo uso de repositórios.

### Análise Crítica

Conclui-se, no final deste estudo, que o *Kodi* apresenta uma arquitetura elaborada e optimamente estruturada.

Entre as diversas perspetivas abordadas, é possivel observar que a equipa do *Kodi* luta por manter o "produto" tão independente quanto possível. Para tal, recorrem a uma estrutura modular. Isto permite uma alteração e agregação de novas *features* de forma rápida, fácil e eficaz, suportando os diversos sistemas operativos e plataformas a que se encontra associado.

É, no entanto, visível que a arquitetura do Kodi tem sido moldada a par das restrições impostas pelas diferentes plataformas, mas com um futuro de prosperidade em mente. Através do uso de ferramentas específicas como o python para os add-ons, as novas funcionalidades podem ser adicionadas sem ser necessário recompilar o código ou sem ter que se preocupar com determinadas dependências de sistemas específicos.

Relativamente aos resultados aqui apresentados, convém salientar que praticamente todos os diagramas apresentados ao longo deste relatório foram construídos pelos respetivos autores do documento (todos à exceção do diagrama da prespectiva modular, o qual foi retirado [deste site](http://delftswa.github.io/chapters/kodi/index.html), assim como algumas das informações presentes neste relatório), recorrendo a documentação fidedigna do projeto *Kodi*. Contudo, é de considerar que diferentes interpretações poderão levar a representações distintas.
