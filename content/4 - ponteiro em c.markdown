Title: Ponteiros em C
image: "/images/criando-lista-encadeada/c-logo.jpg"
Date: 2017-02-15 13:28:47 +0530
Tags: C, Linguagem de programação,Ponteiro C
Category: Estrutura de Dados
Slug: pronteiros-em-c
Author: Mataheus Francisco

![C](/images/ponteiro-em-c/c-logo.jpg)

# Introdução.

FINALMENTE ESTAMOS DE VOLTA...<br>
Falaa galerinha pega aquele café já coloca pra tocar aquele <font color="#0e3ad6">time</font> da <font color="#db0a26">Pink Floyd</font>, que hoje vamos fritar o cérebro, como eu prometi  <strike>79mil anos atrás</strike> hoje vou tentar ensinar o que são esses negócios loucos chamado ponteiro.


# O são ponteiros?

Um ponteiro ( <i>= apontador = pointer</i>)nada mais é do que uma variável que armazena endereço de outras variáveis, como você sabe, cada variável é um local de memória e cada local de memória tem seu endereço definido que pode ser acessado usando o (<b>&</b>). O exemplo abaixo irá imprimir os endereços de memórias das variáveis.<br>


```c
#include <stdio.h>

int main () {

   int  coffe;
   char alotcoffe[10];

   printf("Cade o endereco do coffe: %x\n", &coffe  );
   printf("Cade o endereco de muito coffe uruull: %x\n", &alotcoffe  );

   return 0;
}

```
Outro exemplo : O que é o ponteiro de um relógio? É o que aponta para as horas, minutos ou segundos. Um ponteiro aponta para algo. Em programação, temos as variáveis armazenadas na memória, e um ponteiro aponta para um endereço de memória, essa frase foi retirada.<br>Fonte :[Wikibooks](https://pt.wikibooks.org/wiki/Programar_em_C/Ponteiros)

### Declarando ponteiros.

Utilizamos para declarar um ponteiro <b>type</b> é o tipo do ponteiro, que deve ser um tipo de dados válido em C e o <b>var-name</b> é o nome da variável. O asterisco <b>*</b> é usado para declarar um pointeiro, segue alguns exemplos básicos.


```c
int    *i;    /* ponteiro para um inteiros  */
double *d;    /* ponteiro para um double */
float  *f;    /* ponteiro para um float */
char   *ch;    /* ponteiro para um character */

```

# Como usar ponteiros ~~exemplo-simples~~?

![celula](/images/ponteiro-em-c/EsquemaPonteiro.png)<br>

Para tentar fixar um exemplo de como iremos ou podemos acessar o valor através do endereço de memória, vamos delcarar as variáveis do ponteiro, atribuir o endereço de uma variável a um ponteiro e acessamos o valor no endereço disponível.

```c
#include <stdio.h>

int main () {

   int  a = 20;   /* variavel declarada */
   int  *ip;        /* pontiero tipo inteiro declarado */

   ip = &a;  /* amarmazenamos o endereço da  a em um ponteiro*/

   printf("Endereco da variavel: %x\n", &a  );

   /* endereço armazenado no ponteiro */
   printf("Endereço  na variavel ip: %x\n", ip );

   /* Acessando seu valor usando o ponteiro*/
   printf("Valor da variavel *ip : %d\n", *ip );

   return 0;
}
```
Um outro exemplo bobo sobre ponteiro:

```c
int *p;  // p é um ponteiro para um inteiro
int *q;
p = &a;  // o valor de p é o endereço de a
q = &b;  // q aponta para b
c = *p + *q;
```
Maissss um bobo, só que ilustrado.

![celula](/images/ponteiro-em-c/cpp_ptr_01.gif)
<br>

```c
int var;
int *ptr;
var = 10;
ptr = &var;
```

# Uma falha de segmentação ou em inglês (segmentation fault).

Uma falha de segmentação ou em inglês (segmentation fault) ocorre quando um programa tenta acessar um endereço na memória que está reservado ou que não existe.Nos sistemas Unix quando acontece este tipo de erro o sinal SIGSEGV é enviado ao programa indicando uma falha de segmentação, o ponteiro contem null, definido com o endereço (0x00000000) que causa uma falha de segmentação.<br>
Para que isso não aconteça o ponteiro deve ser inicializado com um endereço válido.


```c

#include <stdio.h>
#include <errno.h>
#include <stddef.h>

int main(void){

  int  a = 5;
  int *p = NULL;
       p = &a;

  /* A operação não é permitida */
  if(p == NULL) return -EPERM ;

     else{

          printf("Endereço a disposição:%p\n", p );
          *p = a; /* Pode colocar 5 */
    }
}
```
NULL está definido dentro do cabeçalho stddef.h . Aqui você não espera que o programa acabe com algum tipo de mágica, se NULL é igual ao valor do ponteiro isso significa que não foi encontrado nem um endereço acessível, então você para, caso contrario você estará executando uma operação que não é permitida. Ou colocar 5 em (0x00000000).
<br>Fonte :[Wikibooks](https://pt.wikibooks.org/wiki/Programar_em_C/Ponteiros) <strike>fique com preguiça de escrever</strike>


# Ponteiro de estrutura ~~loucura loucura~~.

Então como eu não expliquei tudo sobre estrutura vou dar uma passada rápida <strike>because, i'm the fastest man alive</strike>, mas eu prometo que logo faço uma postagem completa de structs...<br>
Na postagem de [lista-encadeada-em-c](https://matheusfrancisco.github.io/como-criar-lista-encadeadas-em-c/) nos criamos uma struct de lista que armazena números inteiros, então agora vamos tentar entender melhor esse tal de ponteiro com outra strcut.

```c
/* temos uma estrutura que armazena nome e idade de uma pessoa */
typedef struct
{
char nome[100];
int idade;
} pessoa;

```

No seguinte código criamos uma pessoa joao e um ponteiro que recebe o endereço de memória de joao, com isso podemos acessar os valores de pessoa joao e alterar como segui no exemplo.<br>

```c
main()
{

pessoa joao;

pessoa *p = &joao;

strcpy(joao.nome, "joao da silva");

joao.idade = 20;

printf("%s, %d\n", (*p).nome, (*p).idade);

(*p).idade = 18;

printf("%s, %d\n", joao.nome, joao.idade);
}
```
O código abaixo tem a mesma função porém substituimos o operdaor <b>(*p)</b> pelo <b> (- <b>></b>)</b>, simplesmente para mostrar que também pode ser utilizado desta maneira.<br>

```c

main()
{
pessoa joao;

pessoa *p = &joao;

strcpy(joao.nome, "joao da silva");

joao.idade = 20;

printf("%s, %d\n", p->nome, p->idade);

p->idade = 18;

printf("%s, %d\n", joao.nome, joao.idade);
}

```

### Vamos tentar complicar um pouco.~~wut~~

Neste código criamos uma struct que  é um produto livro que contém titulo ,autor, editora, ano e numeros de exemplares, com isso podemos fazer o ponteiro percorrer cada um destes valores, também podemos apagar o endereço de memória deletando completamente, utilizar para percorrer quantidade de livros.<br>

```c
typedef struct livro {

 char titulo[60];
 char autor[40];
 char editora[30];
 int ano;
 int num_exemplares;
}produto;


 main()
{
/* variáveis do tipo livro */
 produto livro,livro2,livro3;

produto *p = &livro;

strcpy(livro.titulo, "Ponteiro em C");

livro.ano = 2018;

printf("%s, %d\n", p->titulo, p->ano);

p->ano = 2020; /*podemos atribuir um novo valor para a variavel utilizando o ponteiro*/

printf("%s, %d\n", livro.titulo, livro.ano);
}
```

#### Outra aplicação, Ponteiros como parâmetros de funções.

Neste exemplo, definimos a função swap() como uma função que toma como argumentos dois ponteiros para inteiros; a função faz a troca entre os valores apontados pelos ponteiros. Já na função main(), passamos os endereços das variáveis para a função swap(), de modo que a função swap() possa modificar variáveis locais de outra função. O único possível inconveniente é que, quando usarmos a função, teremos de lembrar de colocar um & na frente das variáveis que estivermos passando para a função.

Se você pensar bem, já vimos uma função em que passamos os argumentos precedidos de &: é a função scanf()! Por que fazemos isso? É simples: chamamos a função scanf() para que ela ponha nas nossas variáveis valores digitados pelo usuário. Ora, essas variáveis são locais, e portanto só podem ser alteradas por outras funções através de ponteiros!

```c
 #include <stdio.h>

 void swap (int *i, int *j)
 {
    int temp;
    temp = *i;
    *i = *j;
    *j = temp;
 }

 int main ()
 {
    int a, b;
    a = 5;
    b = 10;
    printf ("\n\nEles valem %d, %d\n", a, b);
    swap (&a, &b);
    printf ("\n\nEles agora valem %d, %d\n", a, b);
    return 0;
 }
```

## Conclusão
Então pessoal esta postagem foi apenas uma introdução dos ponteiros espero que tenham gostado, foi mais um resumo de como aplicar os ponteiros, pois eu recomendo que peguem exercícios e tentem praticar porque é uma ferramenta muito boa para desenvolvimente com a linguagem c.<br>
Eu gostaria de notificar que irei começar a postar com frequência pelo menos uma vez por semana <strike>no minimo</strike>, vocês podem mandar temas sugestoes e também podem mandar e-mail com exercícios que eu faço uma postagem explicando ou envio pelo email mesmo o exercícios


### Alguns links sobre Ponteiros.

[Wikibooks](https://pt.wikibooks.org/wiki/Programar_em_C/Ponteiros)<br>
[tutorialpoint](https://www.tutorialspoint.com/cprogramming/c_pointers.htm)<br>
[Ponteiro Arquivo](http://www.univasf.edu.br/~criston.souza/algoritmos/arquivos/aula14.pdf)<br>
[Puta_site_massa_](http://www.dca.fee.unicamp.br/cursos/EA876/apostila/HTML/node139.html)<br>




<p><font color="#009999
">Que a força esteja com você.
</font></p>
Abração.
