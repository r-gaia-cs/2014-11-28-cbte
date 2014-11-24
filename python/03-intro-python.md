---
layout: lesson
root: ..
title: Introdução ao Python
---

## Objetivos

- Criação de variáveis
- Operações com variáveis
- Importação de bibliotecas
- Uso de bibliotecas
- Criação de listas
- Seleção de elemento em lista
- Criação de dicionários
- Seleção de elemento em dicionários

## Criação de variáveis

Toda variável possui um nome e um valor associado. Para a criação de uma
variável utilizamos a sintaxe:

~~~
nome_da_variavel = valor_da_variavel
~~~

Vamos criar uma variável que armazena o número zero:


~~~
zero = 0
~~~

## Operações com variáveis

Variáveis podem ser manipuladas. As manipulações mais simples que
podemos fazer são operações aritméticas. Para exemplificar vamos
criar uma variável que armazena o número um e depois vamos realizar
algumas operações aritméticas.

~~~
um = 1
~~~
~~~
zero + um
~~~
~~~
zero - um
~~~
~~~
zero * um
~~~
~~~
um ** zero
~~~
~~~
um / zero
~~~

Também podemos fazer comparações:

~~~
um == zero
~~~
~~~
um > zero
~~~

## Bibliotecas

Bibliotecas ou pacotes são um conjunto de coisas curadas por terceiros que podem
ser utilizados por você. Por exemplo, algumas operações matemáticas estão
agrupadas na biblioteca `math`. Para utilizar uma biblioteca precisamos
importá-la.

~~~
import math
~~~

Para obter informações sobre a biblioteca você pode utilizar
`help(nome_da_biblioteca)`. Para acessar alguma das coisas presentes na
biblioteca utilizamos `nome_da_biblioteca.elemento_desejado`. Vamos obter o seno
e o cosseno de zero.

~~~
math.sin(zero)
~~~
~~~
math.cos(zero)
~~~

## Listas

Listas é uma estrutura de dados de elementos similares.

~~~
primeiros_numeros_naturais = [0, 1, 2, 3, 4]
~~~

Para acessar um elemento de uma lista utilizamos sua posição (começando a contar
de zero).

~~~
primeiros_numeros_naturais[0]
~~~
~~~
primeiros_numeros_naturais[4]
~~~

## Dicionários

Dicionários são outra estrutura de dados organizada por chaves que possuem um
valor associado.

~~~
familia = {"pai": "José", "mãe": "Maria", "filhos": ["Jesus"]}
~~~

O acesso a um valor é feito utilizando a chave.

~~~
familia["pai"]
~~~
~~~
familia["filhos"]
~~~

## Exercícios

1. Crie as variáveis `dez` e `cem` armazenando em cada uma seu valor numérico.
2. Multiplique a variável `dez` por dois e compare o resultado obtido com o valor armazenado na variável `cem`.
3. Calcule a tangente de zero.
