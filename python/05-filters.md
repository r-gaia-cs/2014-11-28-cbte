---
layout: lesson
root: ..
title: Filtrando dados
---

## Objetivos

- Selecionar um conjunto de linhas de um CSV
- Selecionar uma coluna de um CSV
- Selecionar um conjunto de colunas de um CSV
- Selecionar um conjunto de linhas com base no valor de uma das colunas

## Exemplo - Seleção de linhas

**Preparação**: você deve ler os dados de um CSV e salvá-los em uma variável
antes de tentar os exemplos dessa lição.

~~~
meus_dados = pandas.read_csv("example.csv", sep=";", parse_dates=[[0,1]],
               converters={"chamber volume": lambda x: float(x.replace(",",".")),
                           "chamber area": lambda x: float(x.replace(",",".")),
                           "Air C T": lambda x: float(x.replace(",",".")),
                           "Pressure (atm)": lambda x: float(x.replace(",","."))})
~~~

Para selecionar um conjunto de linhas de um CSV você deve informar o pedaço (em
inglês slicing) com as linhas desejadas. Em Python, a sintaxe para slicing é
`início:final:passo` sendo que `início` por ser suprimido se for igual a `0` e `final` pode ser suprimido se for o último pedaço.

Para obter a primeira linha utilizamos

~~~
meus_dados[:1]
~~~

Para obter as cinco primeiras linhas utilizamos

~~~
meus_dados[:5]
~~~

Para obter as linhas 6-10 utilizamos

~~~
meus_dados[5:10]
~~~

Para obter as linhas pares (sendo que a primeira linha corresponde a linha
zero) utilizamos

~~~
meus_dados[::2]
~~~

Para obter as primeiras linhas também pode-se utilizar:

~~~
meus_dados.head()
~~~

e para as últimas linhas:

~~~
meus_dados.tail()
~~~

## Exemplo - Seleção de colunas

Para obter os valores de uma coluna, utilizamos o nome da coluna. Para
selecionar a coluna denominada "Chamber" utilizamos

~~~
meus_dados["Chamber"]
~~~

e para a coluna denominada "Treatment" utilizamos

~~~
meus_dados["Treatment"]
~~~

Para selecionarmos mais de uma coluna utilizamos uma lista com o nome das
colunas desejadas. Para selecionar a coluna denominada `Chamber` e a coluna
denominada `Treatment` utilizamos

~~~
meus_dados[["Chamber", "Treatment"]]
~~~

Também é possível utilizar uma lista com a posição da coluna desejada. O
exemplo anterior pode ser reescrito como

~~~
meus_dados[[1, 2]]
~~~

## Exemplo - Filtros

Podemos comparar uma coluna com um valor, e.g. para comparar a coluna
denominada "Treatment" com o valor "Sem palha" utilizamos

~~~
meus_dados["Treatment"] == "Sem palha"
~~~

e obtemos um "vetor" booleano, i.e. que possui apenas valores verdadeiro ou
falso. Além da comparação de igualdade, `==`, também existe a comparação

- diferente, `!=`;
- menor, `<`;
- menor ou igual, `<=`;
- maior, `>`;
- maior ou igual, `>=`;
- em, `in`.

Podemos utilizar esse "vetor" booleano para obter apenas as linhas na qual a
coluna denominada "Treatment" possui o valor "Sem palha" utilizando

~~~
meus_dados[meus_dados["Treatment"] == "Sem palha"]
~~~

Para a criação de filtros mais complexos podemos utilizar os operadores `&`
ou `|`. Por exemplo, para obter um "vetor" booleano informando de a linha
possui "Chamber" diferente de 5 e "Treatment" igual a "Sem palha" utilizamos

~~~
meus_dados[(meus_dados["Chamber"]) != 5 & (meus_dados["Treatment"] == "Sem palha")]
~~~

No exemplo anterior, **O uso dos parênteses é obrigatório.**

## Exercício

1.  Informe a diferença no resultado obtido por

    ~~~
    meus_dados[["Chamber", "Treatment"]][:5]
    ~~~

    e

    ~~~
    meus_dados[:5][["Chamber", "Treatment"]]
    ~~~

2.  Ao selecionar apenas uma coluna é possível obter os valores válidos nessa
    coluna utilizando o método `unique`.

    Encontre os valores válidos para a coluna "Treatment".

3.  Ao filtrar as linhas é possível obter o número de linhas que satisfizeram o
    filtro através do atributo `shape`.

    Encontre o número de medições feitas na "Chamber" igual a 1 com "Treatment"
    igual a "Sem palha".
