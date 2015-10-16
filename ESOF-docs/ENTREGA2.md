# Relatório ESOF - 2

## *Kodi*

### Levantamento de Requisitos

  O desenvolvimento de um software começa sempre pelo levantamento e análise de requisitos. É fundamental que se construa o software adequado. Para tal, é necessário que os envolvidos no projeto de software saibam exatamente o que é esperado da aplicação a ser construída.

  No caso do *Kodi*, acima de qualquer outro requisito, este projeto tem alguns que deve sempre cumprir. Alguns deles são:
 * Ser fácil de instalar, configurar e manter
 * Possuir uma interface simples e intuitiva
 * Ser capaz de organizar arquivos de áudio e vídeo de uma forma simples
 * Executar ações na GUI com o mínimo de cliques possíveis
 * Ser destinado a um público internacional
 * Ter um *design* apelativo

O *Kodi* é constituído por uma enorme comunidade. O ambiente de interação entre a equipa do *Kodi* e os seus utilizadores é principalmente o forúm. É maioritariamente aqui que a comunicação entre os desenvolvedores e o "ambiente exterior" acontece. Os utilizadores podem tirar dúvidas, submeter bugs que são analisados e corrigidos pelos programadores, ou submeter ideias que depois são discutidas pela comunidade, sendo aceites ou não. Para participar nos fóruns de discussão é necessário registar-se em [*Kodi* - *Register*](http://forum.kodi.tv/member.php?action=register).

Os *bugs* e novas funcionalidades são geridas através de um site do *Kodi* utilizado para o efeito: [*Kodi* - *Trac*](http://trac.kodi.tv/).


#### *Bugs*

Aos utilizadores que reportam os erros, é-lhes pedido que forneçam um relatório específico de modo a que o problema possa ser reproduzido e mais facilmente corrigido.
Os passos para a submissão de bugs encontram-se em [*Kodi* - *Bugs*](http://kodi.wiki/view/HOW-TO:Submit_a_bug_report).

#### Solicitação de Novas Funcionalidades

As ideias para novas funcionalidades, caso os desenvolvedores as achem oportunas, podem ser discutidas no fórum entre utilizadores e desenvolvedores. Antes de fazer uma solicitação de uma nova funcionalidade, é importante primeiro visitar a página [*Kodi* - *Feature Requests*](http://forum.kodi.tv/forumdisplay.php?fid=9), para garantir que essa nova funcionalidade já não tenha sido anteriormente solicitada, de modo a não existirem ideias repetidas. 


### Análise e Negociação de Requisitos

Nem todos os problemas levantados pela comunidade merecem, por parte da equipa *Kodi*, a mesma atenção a nível de tempo e recursos. Para que uma ideia seja posta em prática é necessário que pelo menos um dos desenvolvedores aceite implementá-la, ou que a própria pessoa que teve a ideia tenha a iniciativa de a implementar, fazendo depois um *pull request*.

A equipa responsável pelo *Kodi* com direitos de aceitar *pull requests* verifica então o que foi alterado, e se aceitarem, usam um *bot* para testar a *build* do projeto nas várias plataformas e fazer *merge* no *branch master* se não tiverem ocorrido problemas durante a compilação. 
Existe uma boa comunição entre os desenvolvedores, através de canais privados no IRC, do *slack*, do fórum, do github e de reuniões, o que lhes permite discutirem entre si de modo a chegarem a um consenso na tomada de decisões.
 

### Especificação de Requisitos

Uma das partes importantes do levantamento de requisitos é a sua especificação e documentação, que tem como fim determinar os objectivos do software e as suas restrições associadas, combinando as exigências do utilizador e do sistema. Normalmente, existe um documento que funciona como uma declaração oficial dos requisitos do sistema chamado Documento de Especificação de Requisitos (*Software Requirements Specification* ou SRS ).

O *Kodi* não utiliza, nem mantem, um SRS.

Segundo um dos membros da equipa do *Kodi* em Portugal (https://github.com/hudokkow):
> Simplesmente nunca se mostrou necessário e, muito francamente, não temos pessoal suficiente, tempo ou disposição... Como o *Kodi* é desenvolvido por voluntários, sem clientes no sentido tradicional do termo, nunca achamos necessário tal nível de organização ou compromisso.

Dada a dificuldade em manter mais de 10 milhões de utilizadores satisfeitos, sobretudo porque o *Kodi* corre em inúmeras plataformas, nunca é alterado um componente essencial do software se a alteração não garantir, pelo menos que:
 * A funcionalidade existente mantêm-se ou é melhorada.
 * Se uma das plataformas não sustentar a(s) nova(s) funcionalidade(s) no imediato, espera-se um periodo razoável até que os programadores responsáveis possam implementá-la. Normalmente, programadores de outras plataformas/áreas ajudam no que é possível. Mas, se algo revelar que as limitações da plataforma são impossíveis de ultrapassar, os utilizadores são avisados deste facto e a funcionalidade é adicionada/estendida às restantes plataformas.
 * A funcionalidade tem que ser testada antes de aparecer numa *Release*.

Para manter toda a gente a par do que está a acontecer ou quem está a editar determinadas partes de código, os membros do *Kodi* fazem questão de discutir internamente a melhor solução para cada problema, principalmente quando se fala num dos componentes principais.

Todos os membros da *Team Kodi*, independentemente da sua área de "*expertise*", têm voto sobre o caminho a seguir e as ideias são debatidas até à exaustão. No final, ganha a maioria, mas é dado mais peso à opinião dos programadores principais dessa área, já que são eles que melhor compreendem o caminho a seguir e os ricos a ele associados.

### Validação de Requisitos

A Validação de Requisitos trata, tal como o seu nome indica, da validação quanto à consistência, precisão e contextualização de requisitos levantados nos processos de levantamento e de análise e negociação de requisitos. Após estas duas fases, é necessário verificar se o código funciona como o esperado.

As novas funcionalidades têm que ser testadas antes de aparecer numa *Realease*, e para isso, o *Kodi* conta com alguns milhares de beta-testers não oficiais, dispostos a testar as *Alphas*, *Betas* e *Release Candidates*. 

Para o tratamento de *pull requests*, a equipa do *Kodi* revê o código e usa o [*buildbot* Jenkins](http://jenkins.kodi.tv/) para testar a build do projeto nas várias plataformas. A partir do momento em que não existirem problemas durante a compilação, fazem *merge* no *branch master*. Quando tudo se encontra terminado, o *Release Manager* faz um *feature freeze*, em que não são adicionadas mais funcionalidades ao código, e decide quando lançar as versões *Beta* e *Release Candidate* para serem testadas pelos utilizadores antes da versão final e corrigir o maior número de bugs possíveis. Quando a versão se encontra estável, é lançada a versão final. Se mais tarde forem encontrados bugs são lançadas versões bugfix release, como por exemplo a versão 15.1.

Para além disto, também existem compilações diárias (*nightly builds*) e mensais (*monthly builds*), feitas automaticamente pelo buildbot referido anteriormente.

Como o *Kodi* utiliza um modelo [RERO](https://en.wikipedia.org/wiki/Release_early,_release_often), com um ciclo de cerca de 6 meses, por vezes há funcionalidades que esperam vários ciclos até atingirem a maturidade necessária para serem incluídas numa *Release*. É o caso do [*RetroPlayer*](http://forum.kodi.tv/forumdisplay.php?fid=194), um novo componente que permite transformar o *Kodi* numa consola de jogos.


### Análise Crítica

Observando o histórico de desenvolvimento do *Kodi*, podemos concluir que definição rigorosa de requisitos para a projeto, bem como os métodos adotados para os salvaguardar, tem vindo a influenciar positivamente o seu crescimento.

Através de diversas ferramentas e procedimentos para o controlo das ações executadas por todos os colaboradores do projeto, a equipa *Kodi* é capaz de gerir todas as alterações propostas, contando ainda com um considerável número de *testers* que poderão garantir a robustez do funcionamento do software.

Analisando os métodos adotados, será de destacar o desempenho desta equipa de desenvolvedores, que desde a criação do programa, têm vindo a apresentar novas versões da aplicação com regularidade, incluindo funcionalidades e extras especificamente dedicados às ideias dos seus utilizadores. A implementação do *buildbot*, uma poderosa ferramenta para o controlo das modificações realizadas, foi crucial para garantir o sucesso do projeto, bem como a exploração das potencialidades do *Git*.
