Title:  Criando uma lista encadeada em C
image: "/images/criando-lista-encadeada/c-logo.jpg"
Date: 2017-01-22 16:01:47 +0530
Tags: c, Linguagem de programção
Category:  Estrutura de dados em C
Slug: lista-em-cadeada
Author: Mataheus Francisco


![C](/images/criando-lista-encadeada/c-logo.jpg)

# Introdução.

Falaaaaa galerinha estamos aqui mais uma vez para tentar ensinar algo, então é  o seguinte hoje vamos criar uma lista encadeada na linguagem C, para esse tutorial acredito que vai ser necessário um pré conhecimento de como utilizar ponteiros e sobre estruturas em c <strike>que em breve crio um tutorial de ambos os assuntos</strike>.


# O que é uma lista encadeada?

Uma lista encadeada ( <i>linked list</i>)   representa uma sequência de objetos do mesmo tipo,  ou seja são uma maneira de armazenar dados com estruturas para que o programador possa criar automaticamente um novo local para armazenar dados sempre que necessário. Geralmente o programador utiliza uma definição struct que contém variáveis para guarda informações e um ponteiro para próxima struct do mesmo tipo.

<pre><code>
    ------------------------------              ------------------------------
    |              |             |            \ |              |             |
    |     DATA     |     NEXT    |--------------|     DATA     |     NEXT    |
    |              |             |            / |              |             |
    ------------------------------              ------------------------------
</code></pre>

# Criando uma struct ~~célula~~.

Galerinha primeiro vamos criar nossa struct que a partir de agora iremos chamar de célula, cada célula irá conter um objeto de algum tipo e o endereço da célula seguinte.


```c
struct test {
    int valor;
    struct test *seg;
}
```
![celula](/images/criando-lista-encadeada/celula-de-lista-prox.png)
![celula](/images/criando-lista-encadeada/celula-de-lista-prox.png)
![celula](/images/criando-lista-encadeada/celula-de-lista-prox.png)<br>

Como podemos ver nas imagens nossa estrutura armazena um número inteiro e um ponteiro para a célula seguinte, sendo assim podemos inserir um número inteiro e criar uma  lista <strike>uma estrutura bem simples</strike> .

```c
struct test {
    char nome;
    int idade;
    float cpf;
    struct test *seg;
}
```
Já nessa estrutura podemos armazenar um nome, uma idade e um cpf e criar uma lista de pessoas, que você pode criar métodos de ordenação <font color="red">Heap-Sort</font>, <font color="blue">Merge-Sort</font>,  <font color="green">Quick-Sort</font> entre outros. Com isso você pode ordenar por nome, idade ou qualquer outro critério   de sua escolha <strike>irei escreve sobre esses métodos de ordenação<strike>.
Agora iremos da o nome para a struct pois falamos que iremos chama-la de célula.

```c
 typedef struct test celula;  // célula
```
Pronto nossa struct agora é um <a href="https://www.ime.usp.br/~pf/algoritmos/aulas/footnotes/data-type.html">tipo de dado</a> chamado célula.

# Inserindo na nossa lista.

Agora vamos inserir alguns elementos na nossa lista, porém  nossa lista é uma lista simplesmente encadeada com cabeça para facilitar a inserção pois existem listas simplesmente  encadeada sem cabeça, duplamente encadeadas com e sem cabeça e listas circulares simplesmente encadeadas e duplamente encadeadas, como não quero que fique muito grande o texto <strike>para não ficar chato a leitura</strike>.

```c

main()
         celula c;
          celula*lst;
          c.seg = NULL;
          lst = &c;


/*método de criação de lista com cabeça diferente*/
          celula *LISTA;
          LISTA = malloc (sizeof (celula));/*aloca memória para não perder o endereço*/
          LISTA->seg = NULL; /*nunca esquecer de sempre apontar para null*/
```
Neste trecho criamos uma <font color="blue">célula c</font> que é uma estrutura do tipo test que contém uma variável do tipo int e um ponteiro para célula seguinte, também foi criado uma  <font color="red">célula *lst</font> que recebe  o endereço de memória da <font color="blue">célula c</font>. As vezes convém tratar a primeira célula de uma lista encadeada como um mero marcador de início e ignorar o conteúdo da célula. Nesse caso, dizemos que a primeira célula é a cabeça.

![lst](/images/criando-lista-encadeada/lst_ord.png)

### Inserindo.
Criando uma função para inserir na lista.

```c

void
insere (int x, celula *p)
{
   celula *nova;
   nova = malloc(sizeof (celula));
   nova->valor = x;
   nova->seg = p->seg;
   p->seg = nova;
}
```
Esta função  recebe um número inteiro e o endereço da sua cabeça lst que definimos anteriormente, na primeira linha você cria uma célula nova e aloca memória depois armazenamos o valor inteiro na nova célula <strike>agora  nesta parte vamos tentar imaginar  </strike>, você tem uma célula <font color="red">LST-->NULL</font> em seguida na linha <font color="blue">nova->seg = p->seg</font> sabendo  que <font color="green">célula *p</font> é um  ponteiro que recebeu sua lista LST, então temos que sua nova célula aponta para onde LST esta apontando ou seja para NULL e logo em seguida mudamos o ponteiro dentro de LST para a nova célula <strike> como a lista é com cabeça não precisamos verificar se o inicio é NULL pois temos já um endereço de memória que passamos para LST que foi a célula c</strike>.
Nossa lista fica assim com a primeira inserção <font color="red">LST-->VALOR-->NULL</font>  quando passamos novamente o valor e a lst para inserir vamos estar inserindo entre a LST e o VALOR ou seja nosso VALOR2 será inserido desta maneira  LST-->VALOR2-->VALOR-->NULL.


### Imprimindo a lista simplesmente encadeada

Então pessoal se a parte de inserção não ficou clara como eu mexi nos ponteiros envie um email ou tente desenhar que eu envio os desenho e uma explicação porque agora iremos imprimir os valores inseridos .

```c
void imprime(celula *lst)
{
    celula*aux;
    aux = lst->seg;

    while(aux != NULL){
        printf("%i", aux->valor);
        aux = aux->seg;
    }
}
```
Esta aqui é uma função fácil de entender estamos passando toda nossa lista para ela, ou seja só precisamos iterar sobre ela <strike>caso sua lista seja sem cabeça você precisa verificar antes se o inicio é NULL para não ocorrer erros</strike>.<br>
Então temos um ponteiro <font color="green">célula *aux</font> que vamos iterar sobre a lista e ir imprimindo os valores da lista iremos até ser igual a NULL ou seja enquanto o ponteiro for diferente de NULL imprimimos o valor nunca podemos esquecer de passar o ponteiro para a célula seguinte.

## Conclusão
Então pessoal é só isso irei deixar um código no [hastebin](https://hastebin.com/fusefoyuso.cpp) que está inserindo e imprimindo valores em uma lista simplesmente encadeada, também irei criar um repositório no github onde postarei todos os tipos de estrutura de dados em c para que todos possam contribuir.

### Alguns site sobre lista encadeada.

[Cpprogramming](http://www.cprogramming.com/tutorial/c/lesson15.html)
[Ime-usp](https://www.ime.usp.br/~pf/algoritmos/aulas/lista.html)
[GeekStuff](http://www.thegeekstuff.com/2012/08/c-linked-list-example)
Se alguém quiser mais programa sobre lista ou alguma estrutura de dados em C é só entrar em contato.




<p><font color="#009999
">Que a força esteja com você.
</font></p>
Abração.
