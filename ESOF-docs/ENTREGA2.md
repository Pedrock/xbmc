# Relatório ESOF - 2

## Kodi

### Levantamento de Requisitos

  O levantamento e a análise de requisitos é o início de todo o desenvolvimento de software. É de fundamental importância para que se construa o software certo, ou seja, é necessário, antes de mais nada, que os envolvidos no projeto de software saibam exatamente o que é esperado da aplicação a ser construída.

  Inicialmente, antes de todos os requisitos provenientes dos *stakeholders*, o Kodi tem já ele próprio requisitos que o caracterizam. Dos quais são exemplo:
  - Ser fácil de instalar, configurar e manter
  - Possuir uma interface simples e intuitiva
  - Ser capaz de organizar arquivos de áudio e vídeo de uma forma simples
  - Executar ações na GUI com o mínimo de cliques possíveis
  - Ser destinado a um público internacional
  - Ter um design apelativo

No entanto, os verdadeiros "génios" que fazem com que o kodi cresça e evolua são os *stakeholders*.
O Kodi é bastante dependente dos seus utilizadores, são essencialmente eles que contribuem para uma evolução contínua do media center, reportando bugs e propondo novas funcionalidades. O ambiente de interação entre a equipa do Kodi e os seus usuários é o forúm. É aqui que a comunicaçao entre os desenvolvedores e o "ambiente exterior" acontece. Os utilizadores podem tirar dúvidas, submeter bugs que depois são analizados e corrigidos pelos programadores, ou submeter ideias que depois são analizadas pela comunidade, sendo aceites ou não. Para participar nos fóruns de discussão é necessário registar-se em [Kodi - Register](http://forum.kodi.tv/member.php?action=register).


Os bugs e novas funcionalidades são geridas através de um site do kodi utilizado para o efeito: [Kodi - Trac](http://trac.kodi.tv/).


#### Bugs

Aos utilizadores que reportamr erros é-lhes pedido que forneçam um relatório especifico de modo a que o problema possa ser rastreado.
Os passos para a submissão apropriada de bugs encontram-se em [Kodi - Bugs](http://kodi.wiki/view/HOW-TO:Submit_a_bug_report).

#### Solicitação de Novas Funcionalidades

As ideias para novas funcionalidades, caso os desenvolvedores as achem oportunas, podem ser discutidas no fórum entre utilizadores e desenvolvedores. Antes de fazer qualquer solicitação dealguma funcionalidade, é importante primeiro visitar a página [Kodi - Feature Requests](http://forum.kodi.tv/forumdisplay.php?fid=9), para garantir que essa nova funcionalidade já não tenha sido solicitada, de modo a não existirem ideias repetidas. 


### Análise de Requirimentos e Negociação

Nem todos os problemas levantados pela comunidade merecem, por parte da equipa Kodi, a mesma atenção a nível de tempo e recursos. Para que uma ideia seja posta em prática é necessário que pelo menos um dos desenvolvedores a aceite implementar, ou que a própria pessoa que teve a ideia, tenha a iniciativa de a implementar, fazendo depois um pull request.

A equipa responsável pelo kodi com direitos de aceitar pull requests verifica então o que foi alterado, e se aceitarem, usam um bot para testar a build do projeto nas várias plataformas e fazer merge no branch master se não tiverem ocorridos problemas durante a compilação. 
Existe uma boa comunição entre os desenvolvedores, através do fórum, do github, do blog e de reuniões, o que lhes permitem discutirem entre si de modo a chegarem a um consenso na tomada de decisões.
 

### Especificação de Requisitos

Uma das partes importantes do levantamento de requisitos é a sua especificação e documentação, que tem como fim determinar os objectivos do software e as suas restrições associadas, combinando as exigências do utilizador e do sistema. Normalmente, existe um documento que funciona como uma declaração oficial dos requisitos do sistema chamado Documento de Especificação de Requisitos (*Software Requirements Specification* ou SRS ).

O Kodi não utiliza, nem mantem, um SRS.

Segundo um dos membros da equipa do Kodi em Portugal (https://github.com/hudokkow):
> Simplesmente nunca se mostrou necessário e, muito francamente, não temos pessoal suficiente, tempo ou disposição... Como o Kodi é desenvolvido por voluntários, sem clientes no sentido tradicional do termo, nunca achamos necessário tal nível de organização ou compromisso.

Dada a dificuldade em manter mais de 10 milhões de utilizadores satisfeitos, sobretudo porque o Kodi corre em inúmeras plataformas, nunca é alterado um componente essencial do software se a alteração não garantir, pelo menos que:
- A funcionalidade existente mantêm-se ou é melhorada.
- Se uma das plataformas não sustentar a(s) nova(s) funcionalidade(s) no imediato, espera-se um periodo razoável até que os programadores responsáveis possam implementa-la. Normalmente, programadores de outras plataformas/áreas ajudam no que é possível. Mas, se se revelar que as limitações da plataforma são impossíveis de ultrapassar, os utilizadores são avisados deste facto e a funcionalidade é adicionada/estendida às restantes plataformas.
- A funcionalidade tem que ser testada antes de aparecer numa Release. Para isso o Kodi conta com alguns milhares de beta-testers não oficiais, dispostos a testar as Alphas, Betas e RCs. Ou mesmo, para os mais corajosos, o *buildbot* disponibiliza *builds* todas as noites. As chamadas *nightlies*.

Como o Kodi utiliza um modelo [RERO](https://en.wikipedia.org/wiki/Release_early,_release_often) para as *releases*, com um ciclo de cerca de 6 meses, por vezes há funcionalidades que esperam vários ciclos até atingirem a maturidade necessária para serem incluídas numa Release. É o caso do [*RetroPlayer*](http://forum.kodi.tv/forumdisplay.php?fid=194), um novo componente que permite transformar o Kodi numa consola de jogos.

Para manter toda a gente a par do que está a acontecer ou quem está a tocar em que código, os membros do Kodi fazem questão de discutir internamente a melhor solução para cada problema, principalmente quando se fala num dos componentes principais. Para facilitar essa troca de ideias, matêm canais privados no IRC, slack e no fórum. O github também é usado, mas normalmente apenas numa fase mais avançada.

Todos os membros da Team Kodi, independentemente da sua área de "*expertise*", têm voto sobre o caminho a seguir e as ideias são debatidas até à exaustão. No final, ganha a voz da maioria mas é dado mais "peso" à opinião dos programadores principais dessa área, já que são eles que melhor compreendem o caminho a seguir.

### Validação de Requisitos

A validação de requisitos no Kodi é feita por *Quality Assurance Testers*. A equipa de segurança de qualidade é uma parte essencial do Kodi para garantir o contínuo sucesso do projecto. Esta é responsável por testar os produtos e investigar possíveis problemas que possam surgir durante este processo. Através de relatórios de erros e de *tracking*, ajudam a garantir que os desenvolvedores têm tempo suficiente para corrigir bugs e que são cumpridas as expectativas dos usuários.

Qualquer pessoa que esteja disposta a investir algum do seu tempo para testar funcionalidades e investigar possiveis causas de problemas pode tornar-se um membro da equipa *QA* (também conhecida como *Bug Hunter Squad*). 

Assim que um problema é reportando nos fóruns ou no sistema de *tracking* de *issues Trac*, o dever da equipa *QA* é confirmar se o problema é um bug e, se o for, o seu papel é garantir que ele fica devidamente reportado em *trac*. De seguida, é necessário garantir que o *bug* é atribuído ao desenvolvedor apropriado e acompanhar o processo de correção do mesmo, de modo a garantir que este toma o rumo devido no tempo estipulado. O relatório é considerado responsabilidade do membro da equipa *Quality Assurance Testers* até que seja confirmada a correção deste pelo *tester* encarregue ou pelo usuário que reportou o *bug*. 

A equipa *QA* está também encarregue por fazer testes de regressão. Tendo assim uma *media library* com diversos formatos de teste contra o producto. Os testes de regressão permitem garantir que não surgirão novos defeitos em componentes já analisados.
[Kodi - Assurance Testing](http://kodi.wiki/view/HOW-TO:Help_with_quality_assurance_testing) 

#### Gravidade e Prioridade

Encontrar a gravidade e prioridade correcta para um problema é algo que requer alguma experiência.

De seguida apresentamos alguns exemplos de problemas e das suas possiveis gravidades e prioridades associadas:
  - *Crasher bugs*
    - Deve ter Gravidade = *Critical*
    - Prioridade = *High*
  - Algo que não funciona como esperado
    - Gravidade = *Minor*/*Normal*/*Major*, dependendo de quanto prejudicar a aplicação
    - Prioridade = *Normal*/*High*
  - Problemas de usabilidade
    - Gravidade = *Minor*
    - Prioridade = *Normal*
  - Questões de acessibilidade
    - Gravidade = *Minor*/*Normal*, dependendo da extensão do bug
    - Prioridade = *Normal*
  - *Strings* incorrectas, erros de digitação, etc
    - Gravidade = *Trivial*
    - Prioridade = *Normal*/*High*, dependendo da visibilidade do usuário
  - *Feature requests*
    - Gravidade = *Enhancement*
    - Priority = *Normal*
   (FALTA: Se é realmente um novo recurso, e não uma melhoria do projecto )

No caso de não existir certeza quanto à classificação, é adicionado um comentário que explica o porquê daquela escolha.

### Análise Crítica
