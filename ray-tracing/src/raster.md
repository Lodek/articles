# Rasterização

Na computação gráfica é comum ser utilizados espaços geométricos
virtuais onde são modelados os objetos de um ambiente virtual.
Normalmente esse espaço é definido no $R^3$, logo é possível modelar
primitivas como pontos, retas ou polígonos de maneira contínua. Embora
essas imagens sejam modeladas em um ambiente contínuo existe um porém,
os instrumentos utilizados para a visualização de imagens
computadorizadas são discretos. Por exemplo, um monitor é composto de um
número finito de pixels, pequenos pontos providos de uma única cor,
ordenados em um formato de matrix. A rasterização é a ferramento
utilizada quando é necessário converter um cena descrita de maneira
matemática (também chamada de vetorial) para um modelo discreto
(rasterizado).

Ambientes de computação gráfica como a OpenGL utilizam um modelo
matemático para modelar uma cena 3D. Essas bibliotecas fazem uso da
algebra linear e vetores para representar formas geométricas. Por
exemplo, ao executar a função glBegin(GL_LINES), os pontos informados
dentro da rotina de desenho são combinados para criar vetores que
representam uma linha [@boss]. A combinação de elementos simples como
linhas, pontos e triângulos são utilizados para descrever uma cena no
espaço virtual. De maneira geral, objetos 3D são compostos por malhas de
triângulos que representam sólidos 3D [@boss]. Embora criado esse mundo
virtual, ele é de utilidade ao menos que seja apresentado para o usuário
de alguma maneira.

Atualmente a tecnologia predominante, para não dizer a única, de se
obter uma saída gráfica de um computador são as telas. A sofisticação
das telas e monitores durante os anos é notável, evoluindo desde os
monitores CRT até os monitores baseados em LED dos dias de hoje. Porém
todas seguem um mesmo paradigma, são uma interface 2D compostas por
pixels. As telas são formadas por um conjunto de pixels ordenados em um
formato de matrix onde é possível controlar a cor individual deles. A
rasterização pode ser pensada como um ferramenta onde: dado um mundo 3D
virtual e a posição de um observador, é gerada uma imagem 2D discreta
(formada por pixels). É importante ressaltar que a rasterização por si
só não apresenta métodos para definir a posição de sombras ou reflexos
em uma cena 3D, ao contrário da técnica de ray tracing que apresenta uma
solução completa para a renderização de uma cena [@boss].

Existem várias técnicas e algoritmos de rasterização já criados mas
todos eles atendem a necessidade de gerar uma imagem baseada em uma cena
3D de maneira rápida e dinâmica. Jogos eletrônicos fazem extenso uso das
rasterização para renderizar os mundos virtuais em cenas que possam ser
mostradas por um monitor, por exemplo [@boss]. Devido à contínua melhora
do hardware das GPU o resultado final de imagens rasterizadas está em
constante progresso.

Rasterização é uma técnica usada para converter formas 3D de uma cena
virtual em um conjunto de pixels. Essa conversão faz com que seja
possível visualizar uma ambiente 3D em um tela 2D. As técnicas de
rasterização são muitas porém elas são usadas em situações onde é
necessário ter a visualização de uma imagem em tempo real.
