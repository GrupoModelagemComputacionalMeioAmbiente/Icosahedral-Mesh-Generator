1) CVI0  - codigo para calcular as coordenadas dos vertices da malha delaunay (icosaedral) de 
           nivel 0.
2) CVI   - codigo para calcular as coordenadas dos vertices da malha delaunay (icosaedral) de
           nível 1 em diante.
3) CVD   - codigo para calcular as coordenedas dos vertices da malha voronoi (dual) de qualquer
           nível.
4) CFD   - codigo gerado para construir as faces da malha voronoi (dual) de qualquer nível.
5) GVTKD - Codigo destinado a gerar um arquivo do tipo VTK para vizualização da malha voronoi
           (dual) no pacote paraview.
6) CFV   - codigo criado para encontrar as faces vizinhas (e as arestas comuns dessas faces)
           de uma face dual utilizando a ordenacao feita por CFD.
7) CAAD  - codigo para calcular a área e os comprimentos das arestas da malha voronoi.

OBS.: OS ARQUIVOS DEVEM SER EXECUTADOS NESSA ORDEM.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

cico"i".txt - arquivo que contém as coordenadas da malha icosaedra de nível "i", i=1...6.

========================================
TABELA COORDENADAS ICOSAEDRAL - DELAUNAY
========================================

coord |  x  |  y  |  z
------------------------
  0   | 0.0 | 0.0 | 1.0

coord   - NUMERÇÃO GLOBAL DAS COORDENADAS DA MALHA ICOSAEDRAL.
x, y, z - COORDENADAS CARTESIANAS.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

fico"i".txt - arquivo que contém as faces da malha icosaedra de nível "i", i=1...6.

==================================
TABELA FACES ICOSAEDRAL - DELAUNAY
==================================

face | coord1 | coord2 | coord3
-------------------------------
  0  |   0    |   1    |   2

FACE    - NUMERAÇÃO GLOBAL DAS FACES DA MALHA ICOSAEDRAL.
coord i - CORRESPONDE A NÚMERAÇÃO GLOBAL DAS COORDENDAS ICOSAEDRAL.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

cdual"i".txt - arquivo que contém as coordenadas da malha dual (voronoi) de nível "i", i=1...6.

TABELA COORDENADAS DUAL - VORONOI
=================================

coord |     x    |     y     |    z
---------------------------------------
  0   | 0.390277 |  0.283543 | 0.631481

coord   - NUMERÇÃO GLOBAL DAS COORDENADAS DA MALHA DUAL.
x, y, z - COORDENADAS CARTESIANAS.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

fdual"i".txt - arquivo que contém as faces da malha dual (voronoi) de nível "i", i=1...6.

===========================
TABELA FACES DUAL - VORONOI
===========================

face | coord1 | coord2 | coord3 | coord4 | coord5 | coord6
----------------------------------------------------------
  0  |   0    |   1    |   2    |    3   |    4   |  NE

face    - NÚMERAÇÃO GLOBAL DAS FACES DA MALHA DUAL.
coord i - NUMERAÇÃO GLOBAL DAS COORDENADAS QUE COMPÕEM A FACE DUAL.
NE      - NÃO EXISTE COORDENADA.

obs: as doze primeiras faces tem 5 coordenadas.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

fvizinha"i".txt - arquivo que contém as faces vizinhas a cada face da malha dual (voronoi)
                  de nível "i", i=1...6.

===========================================
TABELA DAS FACES VIZINHAS DA DUAL - VORONOI
===========================================

face | viz1| viz2| viz3| viz4| viz5| viz6
-----------------------------------------
  0  |  2  |  3  |  4  |  5  |  1  | NE
 ... | ... | ... | ... | ... | ... | ...
     |     |     |     |     |     |
  11 |  7  |  8  |  9  |  10 |  6  | NE

face  - NUMERAÇÃO GLOBAL DAS FACES.
viz i - NUMERAÇÃO GLOBAL DAS FACES VIZINHAS.
NE    - NÃO EXISTE FACE VIZINHA.

obs: as doze primeiras faces tem 5 arestas.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

aresta"i".txt - arquivo que contém as arestas comum as faces vizinhas.

================================================
TABELA DAS ARESTAS COMUNS ÀS FACES DUAL VIZINHAS
================================================

face | ares1 | ares2 | ares3 | ares4 | ares5 | ares6
-----------------------------------------------------
  0  |   0   |   0   |   0   |   0   |   0   |  NE
  1  |   4   |   1   |   1   |   4   |   4   |  NE

face   - NUMERAÇÃO GLOBAL DAS FACES DUAL. 
ares i - NUMERAÇÃO LOCAL (i=1...6) QUE CORRESPONDE A ARESTA DA FACE VIZINHA A "face".
	 "ares1" CORRESPONDE A "viz1".

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

arestacomum"i".txt - arquivo que contém as arestas comuns as faces icosaedras vizinhas e
                     quem formam uma face dual.

================================================================================
TABELA DAS ARESTAS COMUNS ÀS FACES VIZINHAS ICOSAEDRAL QUE COMPÕEM UMA FACE DUAL
================================================================================

face | ares1 | ares2 | ares3 | ares4 | ares5 | ares6
-----------------------------------------------------
  0  |   0   |   0   |   0   |   2   |   0   |  NE
  1  |   0   |   0   |   2   |   2   |   0   |  NE

face   - NUMERAÇÃO GLOBAL DAS FACES DUAL.
ares i - NUMERAÇÃO LOCAL (i=1...6) QUE CORRESPONDE A ARESTA COMUM A DUAS FACES VIZINHA
         ICOSAEDRAL QUE COMPÕEM UMA FACE DUAL.

xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

NÍVEL | VÉRTICES | FACES | ARESAS 
  0   |       12 |    20 |     30
  1   |       42 |    80 |    120 
  2   |      162 |   320 |    480
  3   |      642 |  1280 |   1920
  4   |     2562 |  5120 |   7680
  5   |    10242 | 20480 |  30720
  6   |    40962 | 81920 | 122880
