Title: Introdução a redes neurais artificias.
image: "/images/introducao-a-redes-neurais/rna.jpg"
Date: 2017-03-03 16:48:47 +0530
Tags: Redes neurais, Ling. de prog C,Neural Network, RNA
Category: IA
Slug: meu-primeiro-post
Author: Mataheus Francisco

<img src="/images/introducao-a-redes-neurais/rna.jpg" alt="Example" width="200" height="100">




Falaaaa galerinha do bem, tudo certo? Estamos aqui mais uma vez pra fazer aquela postagem marotinha, então pegue
seu <font color="red">café <3</font> coloque pra tocar aquele <font color="red">AC(~~raio~~)DC</font>,<font color="blue"> music: It's a Long Way to the Top(if you wanna rock n' roll) </font> e bora aprende um pouco sobre IA e as tals de redes neurais, já vou logo
avisando esta postagem pode ser mtttttt chatinha..

# Introdução.
Esse negócio de estudar  redes neurais (~~neurocomputação~~) surgiram em 1943, com Warren McCulloch e Walter Pitts, mas o que são redes neurais artificiais - RNA's
basicamente modelos matemáticos inspirados no princípio de funcionamento do neurônio biológico,  elas buscam simular habilidades humanas tais como: aprendizado, generalização, associação
e abstração.

<font color="green"> <h1> Características de uma rede neural.</h1></font>


Como não quero deixar a postagem muito grande vou falar de algumas características de uma RNA alguns pontos que acho importane (~~ou não~~)

<font color="#90179b"> <h3> Busca paralela .</h3></font>
A procura pela informação ocorre de maneira paralela e não sequencial.

<font color="#871f1f"> <h3> Generalização <strike>muito boa</strike>. </h3></font>
Essa é uma das que considero muito boa, pois, é a partir de exemplos anteriores uma RNA é capaz de generalizar seu conhecimento exemplo: enviamos para nossa rede treinar com diversas formas de escrita da letra “A” logo com isso quando escrevermos algo próximo a letra “A” nossa rede ira identificar muito bom né, serve para o alfabeto todo.

Aprendem padrões a partir dos dados que são abstraídos de modelos de conhecimento. O aprendizado é realizado/implementado por um algoritmo de aprendizado.

<font color="#8c0f0f"> <h3> Abstração <strike>muito boa</strike> .</h3></font>
Capacidade de identificar a essência a partir de um conjunto de dados de entrada. A partir de padrões
ruidosos uma RNA pode extrair as informações do padrão se ruído.


<font color="#092321"> <h3> São não programáveis. </h3></font>
Uma RNA deve ser modelada segundo as entradas e saídas envolvidas em um algoritmo de
aprendizado, buscando mapear corretamente as entradas nas saídas correspondentes


<font color="#092321"> <h3> Soluções aproximadas .</h3></font>
Muitas vezes uma RNA produz uma solução aproximada para um determinado problema. As
RNA´s são suscetíveis a geração de soluções incorretas.

<font color="#2c02ff"> <h1> Redes Neurais Artificiais. </h1></font>

Enfim eu estava cansado de dar tando control+C, vamos falar um pouco das RNA's  que são formada
por neurônios artificiais com conexões ponderadas por valores denominados pesos, em uma RNA seus neurônios
são  arrumados em camadas com conexões entre elas que são organizadas em: camada de entrada,
camada de saída e camada intermediária, comumente chamada de camada oculta.

![RNA](/images/introducao-a-redes-neurais/mlp.JPG)
No caso da nossa imagem meramente ilustrativa  de uma rede neural do tipo  MLP (multilayer percptron) temos as camadas de entrada, oculta (~~intermediária~~) e saídas.


Os neurônio artificial é projetado para imitar algumas das principais características de um biológico as entradas de neuro artificial é multiplicada por um peso Qij, gerando entradas ponderadas,
todas as entradas ponderadas são somadas obtendo-se um valor NET que é o potencial de ativação do neurônio artificial. Com isso o valor do NET será comparado ao valor limite para ativação do
neurônio

![Wij](/images/introducao-a-redes-neurais/wij.png)

<font color="#2c02ff"> <h4> Conexões entre neurônios.</h4></font>

Como cada neurônio artificial possui seu valor real chamado peso sináptico,  dependendo do valor do peso maior ou menor será influência positiva ou negativa do neurônio

![conexao](/images/introducao-a-redes-neurais/conexao.png)


<font color="#2c02ff"> <h4> Regra de propagação. </h4></font>

Quando  os estímulos provenientes de outros neurônios são combinados aos pesos sinápticos correspondentes para compor o potencial de  ativação, então
a regra de propagação estabelece o potencial de ativação de um neurônio NET(k), cujo a regra pode ser um produto escalar entre o vetor de entrada e o vetor
de pesos.

![regra](/images/introducao-a-redes-neurais/regra.png)


<font color="#2c02ff"> <h4> Funções de ativação. </h4></font>

Esta é a função que determina o novo valor do estado de ativação do neurônio a partir do potencial de ativação Net(k), assim determina a saída efetiva de um neurônio artificial <font color="red">Sk= F(Netk + bk)</font> onde F é a função de ativação do neurônio e bk é uma constantes que tem efeito de aumentar ou diminuir a entrada líquida da função de ativação, comumente chamada
de bias. Eu irei postar algumas funções utilizadas:
![linear](/images/introducao-a-redes-neurais/linear.png)<br>

![rampa](/images/introducao-a-redes-neurais/rampa.png)<br>

![degrau](/images/introducao-a-redes-neurais/degrau.png)<br>

![bipolar](/images/introducao-a-redes-neurais/bipolar.png)<br>

![sig](/images/introducao-a-redes-neurais/sig.png)<br>

<font color="#2c02ff"> <h4> Arquiteturas de RNA´s </h4></font>
Exitem redes com apenas uma camada de neurônios, múltiplas camadas, redes feedforward( acíclica), redes feddback ( cíclica), redes com recorrência auto-associativa, porém não irei explicar todas aqui
tentarei fazer postagem de desenvolvimento com redes neurais de múltiplas camadas e poucas camadas.

<font color="red"> <h1> Processamento neural </h1></font>

Os processamentos neural artificial pode ser dividio em aprendizado onde é  um processo de atualização dos pesos sinápticos para aquisição do conhecimento, s
os pesos são atualizados conforme o algoritmo de aprendizado escolhido e o vetor de pesos w(t+1) no instante t+1 pode ser escrito com
w(t+1) = w(t) +lw(t), onde lw(t) é o ajuste aplicado aos pesos, podemos falar que os algoritmos de aprendizado diferem na forma de como é calculado lw(t).

O processo de aprendizado possui os seguintes passos:
<br>
* A rede neural é estimulada ao receber um padrão de entrada retirado de um conjunto histórico de padrões ou dados.
* A rede neural sofre modificações em seus parâmetros livres.
* A rede neural responde de uma nova maneira ao ambiente.

Estes passos são repetidos até um critério de parada seja estabelecido, podendo ser: número de iterações máximo atingido ou erro produzido pela rede atinge um patmar abaixo do limiar definido, devemos levar
em consideração que uma rede só pode ser aplicada a um problema após ter sido treinada, na fase de aplicação não há atualizações dos pesos sinápticos

<font color="red"> <h4> Tipos de aprendizdos em rna </h4></font>

Temos aprendizado supervisionado, onde os pesos sinápticos são atualizados até que o valor do erro fique abaixo de um limite máximo de tolerância especificado
pelo usuário.

![super](/images/introducao-a-redes-neurais/super.png)<br>

Este tipo de aprendizado envolve a minimização da soma dos erros quadráticos das saídas.

![erro](/images/introducao-a-redes-neurais/nsuper.png)<br>

Também temos os não supervisionado trabalha os dados de maneira a determinar algumas propriedades dos conjuntos de dados  não existe para cada entrada uma saída desejada, regularidade
e redundância nas entradas são características essenciais para haver aprendizado não supervisionado. Esse tipo de aprendizado é muito útil para agrupamento de dados e temos o aprendizado por reforço que é útil
para aplicação de tarefas de controle, porém não irei falar muito que a postagem já ficou muito chatinha.





<font color="#37124f"> <h1> Conclusão </h1></font>

Então galerinha estou aqui para concluir essa pequena introdução de redes neurais que podem ser utilizadas para os seguintes problemas: classificação de padrões, reconhecimento de padrões, correção de padrões, previsão de séries temporais,
 mineração de dados e suporte à decisão. Meus queridos como essa introdução ficou muito longa vou deixar um link de uma rede neural simples que fiz, onde irei na próxima postagem escrever sobre o desenvolvimento dela.
  [Rede Neural utilizando perceptron para identificar compositores e cientistas](https://github.com/matheusfrancisco/perceptron/blob/master/Perceptron.c)

# Referências

Um Introdução a Inteligência Computacional: fundamentos, ferramentas e aplicações. GOLDSCHIMIDT, R. L. Rio de Janeiro, 2010.
Editora IST-RJ.

<p><font color="#009999
">Que a força esteja com você.
</font></p>
Abração.

