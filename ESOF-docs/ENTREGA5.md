# Relatório ESOF - 5

## *Kodi* - Evolução do Software

### Introdução

Neste relatório iremos analisar o *Kodi* relativamente à evolução do seu *software*. 

Para finalisação do projeto desenvolvido no âmbito de Engenharia de Sotware, foi-nos pedido a implementação ou melhoria de uma funcionalidade. Para isto, os autores deste relatório começaram por identificar a nova funcionalidade a desenvolver e posteriormente, a sua implementação.
Neste relatório, será apresentada a nova funcionalidade implementada bem como algumas considerações finais acerca do *Kodi*.

### Identificação da Funcionalidade

O *Kodi* apresenta uma vasta lista de [*issues*](http://trac.kodi.tv/report) à espera de serem corrigidos, assim como novas [*features*](http://forum.kodi.tv/forumdisplay.php?fid=9) a serem implementadas.
Quer as novas *features* quer os *issues* são descobertos pelos colaborados e pelos próprios utilizadores do *Kodi*, como já referido em [relatórios anteriores](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/ENTREGA2.md). Após uma análise destas duas listas, o decidimos implementar uma nova funcionalidade que tem por base a seguinte [*thread*](http://forum.kodi.tv/showthread.php?tid=238563) do fórum do *Kodi*. Esta funcionalidade pretende organizar o actor de acordo com o número de filmes presentes na biblioteca.



#### Identificação dos Componentes que Implementam a Funcionalidade

#### Submissão de um Pull Request

Depois da implementação da nova funcionalidade, foi [submetido um *pull request*](https://github.com/xbmc/xbmc/pull/8576) para que seja possível a integração da nova funcionalidade no projeto.

#### Análise Crítica

A implementação deste funcionalidade, apesar de parecer simples à primeira vista, revelou-se complexa devido à extensão em termos de código do *Kodi*, o que tornou a procura pelos componentes relacionados com a *feature* demorosa.

O *Kodi*, devido à sua enorme estrutura e quantidade de código presente, assim como ao seu baixo grau de Isolabilidade, torna difícil a tarefa dos colaboradores, pois estes necessitam de conhecer bem o projecto para tornar produtiva a elaboração de código em relação ao tempo gasto. 

O *Kodi* apresenta grande potencial devido a ser um projeto *open-source* e suportar diferentes plataformas,encontra-se constantemente em desenvolvimento e qualquer pessoa que tenha interesse e motivação pode contribuir de acordo com as suas competências.
