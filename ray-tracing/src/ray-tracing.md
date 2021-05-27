# Ray Tracing

Na computação gráfica as técnicas de ray tracing são utilizadas para
renderizar uma cena 3D. Uma das características mais notáveis do ray
tracing é que a partir dele é possível gerar cenas extremamente
detalhadas e realistas. Nesse estudo será abordado de maneira geral o
que é o ray tracing, qual problema ele resolve e suas características.

Segundo @boss, ray tracing é uma técnica unificada que realiza o cálculo
de luminosidade e sombra, eliminação de objetos escondidos, reflexão e
transmissão de luz, sombreamento e outros efeitos. Essa poderosa técnica
é capaz de gerar imagens extremamente detalhadas, capaz de imitar o
mundo real. Para tanto, a ideia central do ray tracing é literalmente
simular o comportamento de um raio de luz. Essa simulação é feita
traçando os raios de luz que atingem um observador de volta para a fonte
de luz emissora. A primeiro momento isso pode soar estranho e invertido,
afinal os raios de luz são emitidos pelas fontes e não pelo observador.
A justificativa para isso é que: considerando uma fonte de luz pontual
idealizada, a mesma emite raios de luz em todas as direções de maneira
uniforme, sendo assim somente uma parcela muito pequena desses raios
chegarão ao observador [@boss]. Sendo assim, para economizar recursos
computacionais é feito o trabalho reverso: dado um observador, qual foi
o caminho percorrido por um determinado raio de luz até atingi-lo.

Sabendo que o ray tracing é feito a partir de uma simulação do
comportamento dos raios de luz, isso ainda não explica como a cena será
transformada em pixels. Para isso basta colocarmos uma viewport entre o
observador e a cena. A viewport irá delimitar o limite do que será visto
na cena e define uma grade com os pixels da cena. A técnica de ray
tracing traça um raio de luz para cada pixel na viewport, onde esse raio
normalmente atravessa o centro do pixel [@boss]. Em sumário o ray
tracing é uma técnica que calcula o caminho inverso de um raio de luz
que chega a um observador, cada raio de luz está associado a um pixel e
a cena final é gerada a partir do resultado da simulação de cada raio.

Visto como funciona o ray tracing, precisamos entender o que é feito
para cada raio de luz. Um raio de luz idealizado é emitido por uma fonte
de luz e se propaga de maneira retilínea até colidir com uma superfície.
Nessa colisão parte desse raio de luz é absorvido, parte é refletido e
parte é refratado, sendo esse comportamento determinado pelo material da
superfície que o raio atingiu [@halliday]. Sendo assim, para cada raio
de luz o algoritmo de ray tracing detecta onde esse raio colide com um
objeto da cena onde é determinada a cor da superfície a partir da
luminosidade local e propriedades do material e cria-se dois novos raios
a partir dele, sendo um refletido e outro refratado [@boss]. Esse
processo de traçar os raios é seguido de maneira recursiva para os raios
filhos e a cor final do pixel associado ao raio inicial é dado a partir
da combinação do resultado de todos os raios refletidos e refratados
criados [@boss].

Nota-se que para cada raio de luz do algoritmo de ray tracing o mesmo
cria dois novos raios e esse processo pode-se repetir indefinitivamente
e assim chegamos no principal problema do raytracing, ele é
computacionalmente custoso. Para melhorar o resultado final de imagem
deve-se aumentar o limite da recursão dos raios. Segundo @boss, a média
de tempo para renderizar um frame em um filme é de uma hora, esse número
pode chegar até 10 horas para cenas detalhadas. Cenas geradas com
raytracing demandam muito computacionalmente e não são adequadas para
ambientes onde é feita a computação em tempo real, tal como jogos. O ray
tracing sucede em usos onde toda a computação pode ser feita de antemão.

Em conclusão, a técnica de ray tracing oferece uma solução completa para
o processo de renderização de uma cena. Essa técnica faz uso de um
algoritmo recursivo que simula o comportamento de raios de luz no mundo
real. O algoritmo reconstroi um raio de luz para cada pixel da viewport
que representa a cena. O raio de luz é reconstruído a partir da
identificação das colisões que ele fez com os objetos da cena. A técnica
de ray tracing produz resultados fantásticos porém é computacionalmente
custosa. Avanços em hardware farão com que seja possível gerar cenas
cada vez mais realistas porém essa técnica não é adequada para jogos ou
aplicações que precisem de renderização em tempo real.
