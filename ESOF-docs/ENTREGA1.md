# Relatório ESOF - 1

## Kodi

### Descrição

O Kodi Entertainment Center, ou simplesmente Kodi (anteriormente XBMC) é um projeto multiplataforma gratuito desenvolvido pela XBMC Foundation com vários colaboradores localizados por todo mundo, comunicando online através do Github. 

![Kodi - Image](http://kodi.tv/wp-content/uploads/kodi_about.jpg)

Kodi permite aos utilizadores ver filmes, musica e fotografias através da sua interface elegante e fácil de usar. É um media center que tem como objetivo ser utilizado numa televisão na sala de estar. Além disto, a plataforma permite o uso de inúmeros add-ons, que permitem adicionar novas funcionalidades ao programa, tais como ir buscar media a sites externos, como ao Youtube, por exemplo. Estes add-ons são atualizados automaticamente pelo programa pelo uso de repositórios. Os add-ons são desenvolvidos na linguagem Python, enquanto que o programa é desenvolvido maioritariamente em C e C++.


### Processo

O Kodi é constituído por uma grande comunidade.

Atualmente, o conselho de administração da XBMC Foundation é constituído por 5 pessoa, eleitas pela comunidade. Para além destes, existe um *release manager* eleito para cada *release*, geralmente um membro senior. Contribuem também algumas dezenas de programadores divididos em várias categorias (geral ou por plataforma) e alguns artistas e *testers*. Apenas alguns dos programadores conseguém fazer commits ou aceitar pull requests. Os utilizadores podem submeter bugs que depois são analizados e corrigidos pelos programadores, ou submeter ideias que depois são analizadas pela comunidade, sendo aceites ou não.

Os bugs e novas funcionalidades são geridas através de um site do kodi utilizado para o efeito: [Kodi - Trac](http://trac.kodi.tv/).

Para resolver um bug ou adicionar uma funcionalidade, um utilizador do github deve criar um fork, alterar o código necessário e fazer um pull request. A equipa responsável pelo kodi com direitos de aceitar pull requests então verifica o que foi alterado, e se aceitarem, usam um bot para testar a build do projeto nas várias plataformas e fazer merge no branch master se não tiverem ocorridos problemas durante a compilação.

A equipa do Kodi atribui um nome e várias funcionalidades e correções de bug a cada versão *major*. Temos por exemplo, a versão 15.0 com o nome Isengard. Quando tudo se encontra terminado, o *Release Manager* faz um *feature freze*, em que não são adicionadas mais funcionalidades ao código, e decide quando lançar as versões *Beta* e *Release Candidate* para serem testadas pelos utilizadores antes da versão final e corrigir o maior número de bugs possíveis. Quando a versão se encontra estável, é lançada a versão final. Se mais tarde forem encontrados bugs são lançadas versões *bugfix release*, como por exemplo a versão 15.1.

Para além disto, também existem compilações diárias (*nightly builds*) e mensais (*monthly builds*).

Apesar de este projeto não ter uma metodologia de desenvolvimento bem definida, como a maior parte dos projetos open-source, consideramos que segue o modelo *Agile*. Isto porque existe uma boa comunição entre os desenvolvedores, através do fórum, do github, do blog e reuniões e porque vão sendo lançadas várias versões estáveis ao longo do tempo, cada vez com mais funcionalidades. Também existe uma preocupação em receber *feedback* de parte dos utilizadores. Para além disto, o software encontra-se bem modularizado e uma das preocupações do projeto é manter o código simples, elegante e fácil de manter.

### Análise Crítica

Após a análise do projeto, consideramos que, para um projeto open-source e com tantas plataformas suportadas, está bem estruturado e organizado. Passados vários anos após o início do desenvolvimento, vai suportanto novas plataformas e abandonando outras já obsoletas, enquanto que cada vez mais funcionalidades vão sendo adicionadas. Para além disto, o software também se tem tornado mais estável e fácil de usar. Isto deve-se ao empenho da fundação, sem fins lucrativos, e dos desenvolvedores, que contribuem voluntáriamente de forma a melhorar este *software*.

Na opinião dos autores deste relatório, o processo de desenvolvimento adoptado pela *XBMC Foundation* para o desenvolvimento do *Kodi* é adequado e permite que o *software* seja desenvolvido de forma constante e com resultados visíveis para os utilizadores, permitindo ao mesmo tempo, que os mesmos também contribuam, reportando bugs encontrados e sugerindo funcionalidades, ao usar os diversos tipos de compilação do software, desde as *nightly builds* até às versões estáveis.
