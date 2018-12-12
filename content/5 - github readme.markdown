Title:  Como escrever um readme no github
image: "/images/criando-lista-encadeada/c-logo.jpg"
Date: 2017-01-17 13:01:47 +0530
Tags: github
Category: github
Slug: como-escrever-um-readme
Author: Mataheus Francisco

![Github](http://octodex.github.com/images/minion.png)


## Introdução

Fala galerinha do bem, hoje eu gostaria de explicar para você como escrever um bom readme.md no github, por mais que este 
seja um tutorial básico espero que ajude na questão de lugares para pesquisar.
Então para começar sabemos que o github funciona com markdown ou seja para escrever um bom readme.md você deve aprender um 
pouco das syntax do [markdown](https://daringfireball.net/projects/markdown/syntax).


## O que é markdown ?

Markdown é uma linguagem simples de marcação originalmente criada por John Gruber e Aaron Swartz . Markdown converte seu texto em XHTML válido.


## Syntax

# Heading 
<pre><code>
# h1 Heading
## h2 Heading
### h3 Heading
#### h4 Heading
##### h5 Heading
###### h6 Heading
</code></pre>

# H1

## H2

### H3

#### H4

##### H5

Alternativa aos heading

<pre><code>
TEST
====
Test
-------
</code></pre>

TEST
====

Test
------

##Ênfases

<pre><code>
Itálico *asterisco*  ou _underscores_.

Negrito ,  **astericos** or __underscores__.

Negrito e itálico **astericos e _underscores_**.

Strikethrough Riscos  ou tachado. ~~Scratch this.~~
</code></pre>

Itálico *asterisco*  ou _underscores_.

Negrito ,  **asteriscos** or __underscores__.

Negrito e itálico **asteriscos e _underscores_**.

Strikethrough Riscos  ou tachado. ~~Scratch this.~~


## Links

<pre><code>
[Esse link](http://example.net/)
[About](/about/)



 Usando o atalho de nome de link implícito, você poderia escrever:
[1]: http://google.com/        "Google"
[2]: http://search.yahoo.com/  "Yahoo Search"
[3]: http://search.msn.com/    "MSN Search"
</code></pre>


## Code
<pre><code>
        ```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

```python
s = "Python syntax highlighting"
print s
```
</code></pre>

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
```python
s = "Python syntax highlighting"
print s
```

## Imagens

<pre><code>
Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"

![Minion](http://octodex.github.com/images/minion.png)

![Alt text](http://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")
</code></pre>

Inline-style: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")

Reference-style: 
![alt text][logo]

[logo]: https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 2"


![Alt text](http://octodex.github.com/images/stormtroopocat.jpg "The Stormtroopocat")


##Tabelas

<pre><code>
| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |
</code></pre>

| Option | Description |
| ------ | ----------- |
| data   | path to data files to supply the data that will be passed into templates. |
| engine | engine to be used for processing templates. Handlebars is the default. |
| ext    | extension to be used for dest files. |

## Citações de bloco

<pre><code>
Uma citação
> Que a força esteja com você.
> I love coffe
</code></pre>

Uma citação
> Que a força esteja com você. <br>
> I love coffe <br>

## Conclusão

Então pessoal espero que gostem, pois tentei trazer algo simples para que vocês tenha uma noção do básico assim, podem pegar na parte de referência que tem coisas completas e bem complexas como criação de sumários, adicionar vídeos e etc..<br>
Aqueleeeee abração

>Que a força esteja com você.




### Referências
[Wiki](https://pt.wikipedia.org/wiki/Markdown)<br>
[Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)<br>
[Markdonw-syntax](https://daringfireball.net/projects/markdown/syntax#precode)<br>
[Markdown-syntax-lear](https://learn.getgrav.org/content/markdown)<br>
[Basic-markdown](https://guides.github.com/features/mastering-markdown/)<br>
