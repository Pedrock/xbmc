# Relatório ESOF - 5

## *Kodi* - Evolução do Software

### Introdução

Neste relatório iremos analisar o *Kodi* relativamente à evolução do seu *software*. 

Para a finalização do projeto desenvolvido no âmbito de Engenharia de Sotware, foi-nos pedido a implementação ou melhoria de uma funcionalidade. Para isto, os autores deste relatório começaram por identificar a nova funcionalidade a desenvolver e posteriormente, a sua implementação.
Neste relatório será apresentada a nova funcionalidade implementada bem como algumas considerações finais acerca do *Kodi*.

### Identificação da Funcionalidade

O *Kodi* apresenta uma vasta lista de [*issues*](http://trac.kodi.tv/report) à espera de serem corrigidos, assim como novas [*features*](http://forum.kodi.tv/forumdisplay.php?fid=9) a serem implementadas.
Quer as novas *features* quer os *issues* são descobertos e tratados pelos colaborados ou mesmo até pelos próprios utilizadores do *Kodi*, como já referido em [relatórios anteriores](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/ENTREGA2.md). Após uma análise destas duas listas, decidimos implementar uma nova funcionalidade que tem por base a seguinte [*thread*](http://forum.kodi.tv/showthread.php?tid=238563) do fórum do *Kodi*. Esta funcionalidade pretende organizar os atores de acordo com o número de filmes presentes na biblioteca.

Tivemos que alterar vários ficheiros para implementar a funcionalidade. As alterações podem ser vistas nos [ficheiros alterados do pull request](https://github.com/xbmc/xbmc/pull/8576/files).

Abaixo mostramos duas imagens do resultado da nossa implementação:

![Sort By Number Of Movies](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/sort-by-number-of-movies.jpg)

![Sorted Actors](https://github.com/Pedrock/xbmc/blob/master/ESOF-docs/Images/sorted-actors.jpg)

#### Identificação dos Componentes que Implementam a Funcionalidade

- Incluímos o novo campo de número de filmes em **VideoDatabase**, **DatabaseUtils** e **VideoInfoTag**;
- Adicionámos a escolha do novo tipo de ordenação em **GUIViewStateVideo**;
- Adicionámos a nova ordenação em **SortUtils**;
- Adicionámos a indicação do número de filmes de cada autor aquando da utilização da nova ordenação em **LabelFormatter**;
- Adicionámos a *string* para a nova ordenação em **resource.language.en_gb**.

#### Submissão de um Pull Request

Depois da implementação da nova funcionalidade, foi [submetido um *pull request*](https://github.com/xbmc/xbmc/pull/8576) para que seja possível a integração da nova funcionalidade no projeto.

Obtivemos algumas críticas/sugestões por parte da equipa do *Kodi* e procedemos à alteração do código de forma a cumprir com o pedido.

#### Análise Crítica

A implementação deste funcionalidade, apesar de parecer simples à primeira vista, revelou-se complexa devido à extensão do código do *Kodi*, o que tornou a procura pelos componentes relacionados com a *feature* demorosa. O *Kodi*, devido à sua enorme estrutura e quantidade de código, assim como ao seu baixo grau de isolabilidade, torna difícil a tarefa dos colaboradores, pois estes necessitam de conhecer bem o projecto de forma a tornar produtiva a elaboração de código. 

Outro dos problemas que tivemos, já referido no relatório anterior, foi o facto de não termos conseguido compilar o código em *Windows*, devido a diversas dependências, o que fez com que tivéssemos que usar *Ubuntu* para o efeito. Isto tornou o processo ainda mais demoroso, pois as ferramentas existentes em *Linux* não são tão poderosas como o *Visual Studio* em *Windows*. Por este motivo, analisámos o código em *Windows* e procedemos à alteração em *Linux*.

No entanto, este apresenta grande potencial devido a ser um projeto *open-source* e suportar diferentes plataformas. Encontra-se constantemente em desenvolvimento e qualquer pessoa que tenha interesse e motivação pode contribuir de acordo com as suas competências.
