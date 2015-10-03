# Relatório 1

## Descrição

O Kodi Entertainment Center, ou simplesmente Kodi (anteriormente XBMC) é um projeto multiplataforma gratuito desenvolvido pela XBMC Foundation com vários colaboradores localizados por todo mundo, comunicando online através do Github. 

Kodi permite aos utilizadores ver filmes, musica e fotografias através da sua interface elegante e fácil de usar. É um media center que tem como objetivo ser utilizado numa televisão na sala de estar. Além disto, a plataforma permite o uso de inúmeros add-ons, que permitem adicionar novas funcionalidades ao programa, tais como ir buscar media a sites externos, como ao Youtube, por exemplo. Estes add-ons são atualizados automaticamente pelo programa pelo uso de repositórios. Os add-ons são desenvolvidos na linguagem Python, enquanto que o programa é desenvolvido maioritariamente em C e C++.


## Processo

O Kodi é constituído por uma grande comunidade.

Atualmente, a equipa de gestão do Kodi é constituída por 5 pessoas. Para além destes, existem 3 gestores de projeto, algumas dezenas de programadores divididos em várias categorias (geral ou por plataforma) e alguns artistas e *testers*. A equipa de gestão é votada pela comunidade, sendo a maior parte também desenvolvedores do Kodi. Apenas alguns dos programadores conseguém fazer commits ou aceitar pull requests. Os utilizadores podem submeter bugs que depois são analizados e corrigidos pelos programadores, ou submeter ideias que depois são analizadas pela comunidade, sendo aceites ou não.

Os bugs e novas funcionalidades são geridas através de um site do kodi utilizado para o efeito: [Kodi - Trac](http://trac.kodi.tv/).

Para resolver um bug ou adicionar uma funcionalidade, um utilizador do github deve criar um fork, alterar o código necessário e fazer um pull request. A equipa responsável pelo kodi com direitos de aceitar pull requests então verifica o que foi alterado, e se aceitarem, usam um bot para testar a build do projeto nas várias plataformas e fazer merge no branch master se não tiverem ocorridos problemas durante a compilação.

A equipa do Kodi atribui um nome e várias funcionalidades e correções de bug a cada versão *major*. Temos por exemplo, a versão 15.0 com o nome Isengard. Quando tudo se encontra terminado, fazem um *feature freze*, em que não são adicionadas mais funcionalidades ao código, e lançam versões *Beta* e *Release Candidate* para serem testadas pelos utilizadores antes da versão final e corrigir o maior número de bugs possíveis. Se mais tarde forem encontrados bugs são lançadas versões *bugfix release*, como por exemplo a versão 15.1.

Para além disto, também existem compilações diárias (*nightly builds*) e mensais (*monthly builds*).

Apesar de este projeto não ter uma metodologia de desenvolvimento bem definida, como a maior parte dos projetos open-source, consideramos que segue o modelo *Agile*. Isto porque existe uma boa comunição entre os desenvolvedores, através do fórum, do github, do blog e reuniões e porque vão sendo lançadas várias versões estáveis ao longo do tempo, cada vez com mais funcionalidades. Também existe uma preocupação em receber *feedback* de parte dos utilizadores. Para além disto, o software encontra-se bem modularizado e uma das preocupações do projeto é manter o código simples, elegante e fácil de manter.

## Análise Crítica
