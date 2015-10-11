# Relatório ESOF - 2

## Kodi

### Levantamento de Requisitos

  O levantamento e a análise de requisitos é o início para todo o desenvolvimento de software. É de fundamental importância para que se construa o software certo, ou seja, é necessário antes de mais nada que os envolvidos no projeto de software saibam exatamente o que é esperado do aplicativo a ser construído.

  Primeiramente e antes de todos os requisitos provenientes dos *stakeholders*, o kodi tem já ele próprio requisitos que o caracterizam. Dos quais são exemplo:
  - Ser fácil de instalar, configurar e mater
  - Possuir uma interface simples e intuitiva
  - Ser capaz de organizar arquivos de áudio e vídeo de uma forma simples
  - Executar ações na GUI com o mínimo de cliques possíveis
  - Ser destinado a um público internacional
  - Apelativo ao olhar


No entanto, os verdadeiros "génios" que fazem com que o kodi cresça e evolua são os *stakeholders*.
O Kodi é bastante dependente dos seus usuários, são especialmente eles que contribuem para uma evolução contínua do media center, relatando bugs e propondo novas funcionalidades. O ambiente de interação entre a equipa do Kodi e os seus usuários é o forúm. É aqui que a comunicaçao entre os desenvolvedores e o "ambiente exterior" acontece. Os usuários podem tirar dúvidas, submeter bugs que depois são analizados e corrigidos pelos programadores, ou submeter ideias que depois são analizadas pela comunidade, sendo aceites ou não. Para participar nos foruns de discussão é necessário registar-se em [Kodi - Register](http://forum.kodi.tv/member.php?action=register).


Os bugs e novas funcionalidades são geridas através de um site do kodi utilizado para o efeito: [Kodi - Trac](http://trac.kodi.tv/).


#### Bugs

Aos usuários que relatam erros é-lhes pedido que forneçam um relatório especifico de modo a que o problema possa ser rastreado.
Os passos para a submissão apropriada de bugs encontram-se em [Kodi - Bugs](http://kodi.wiki/view/HOW-TO:Submit_a_bug_report).

#### Solicitação de Novas Funcionalidades

As ideias para novas funcionalidades, caso os desenvolvedores as achem oportunas, podem resultar em debates entre usuários e desenvolvedores, que decorrem no fórum. Antes de fazer qualquer solicitação de  alguma funcionalidade é importante primeiro visitar a página [Kodi - Feature Requests](http://forum.kodi.tv/forumdisplay.php?fid=9), para garantir que essa nova funcionalidade já não tenha sido solicitada, de modo a não existirem ideias repetidas. 


### Análise de Requirimentos e Negociação

Nem todos os problemas levantados pela comunidade merecem, por parte da equipa Kodi, a mesma atenção a nível de tempo e recursos. Para que uma ideia seja posta em prática é necessário que pelo menos um dos desenvolvedores a aceite implementar. Ou que a própria pessoa que teve a ideia tenha também a iniciativa de a implementar, fazendo depois um pull request.

A equipa responsável pelo kodi com direitos de aceitar pull requests verifica então o que foi alterado, e se aceitarem, usam um bot para testar a build do projeto nas várias plataformas e fazer merge no branch master se não tiverem ocorridos problemas durante a compilação. 
Existe uma boa comunição entre os desenvolvedores, através do fórum, do github, do blog e de reuniões, o que lhes permitem discutirem entre si de modo a chegarem a um consenso na tomada de decisões.
 

### Especificação de Requirimentos

(diagramas...)

### Validação de Requisitos

A validação de requisitos no Kodi é feita por *Quality Assurance Testers*. A equipa de segurança de qualidade é uma parte essencial do Kodi para garantir o contínuo sucesso do projecto. Esta é responsável por testar os produtos e investigar possíveis problemas que possam surgir durante este processo. Através de relatórios de erros e de *tracking*, ajudam a garantir que os desenvolvedores têm tempo suficiente para corrigir bugs e que são cumpridas as expectativas dos usuários.

Qualquer pessoa que esteja disposta a investir algum do seu tempo para testar funcionalidades e investigar possiveis causas de problemas pode tornar-se um membro da equipa *QA* (também conhecida como *Bug Hunter Squad*). 

Assim que um problema é relatado nos fóruns ou no sistema de *tracking* de *issues Trac*, o dever da equipa *QA* é confirmar se o problema é um bug e, se o for, o seu papel é garantir que ele fica devidamente relatado em *trac*. Seguidamente, é necessário garantir que o *bug* é atribuído ao desenvolvedor apropriado e acompanhar o processo de correção do erro, de modo a garantir que este toma o rumo devido no tempo estipulado. O relatório é considerado responsabilidade do membro da equipa  *Quality Assurance Testers* até que seja confirmada a correção deste pelo *tester* encarregue ou pelo usuário que reportou o *bug*. 

A equipa *QA* está também encarregue por fazer testes de regressão. Tendo assim uma *media library* com diversos formatos de teste contra o producto. Os testes de regressão permitem garantir que não surgirão novos defeitos em componentes já analisados.
[Kodi - Assurance Testing](http://kodi.wiki/view/HOW-TO:Help_with_quality_assurance_testing)


### Análise Crítica
