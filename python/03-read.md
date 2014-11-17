---
layout: lesson
root: ..
title: Lendo dados
---

## Objetivos

- Ler dados de um CSV com Pandas.

## Exemplo

Em Python você pode abrir um arquivo utilizando a função `open()`. Se você
quiser imprimir as cinco primeiras linhas você pode utilizar algo como:

~~~
with open("data.csv", "r") as arquivo:
    numero_da_linha = 0
    for linha in arquivo:
        print(linha)
        numero_da_linha += 1
        if numero_da_linha > 4:
            break
~~~

Não se preocupe com o que cada instrução no exemplo anterior significa. Pandas
possui [várias funções para ler
arquivos](http://pandas.pydata.org/pandas-docs/stable/io.html) em vários
formatos incluindo CSV, HDF, SQL, JSON, HTML e até "Excel". Para ler nosso
arquivo CSV podemos utilizar

~~~
pandas.read_csv("data.csv")
~~~

Você irá notar que a tabela obtida apresenta alguns problemas. Esses problemas
decorrem do fato de CSV significar "comma separate values" ou "valores separados
por vírgula" e por esse motivo Pandas utiliza `,` como o separador padrão das
colunas. Como nosso arquivo utiliza `;` para separa as colunas precisamos
informar isso para o Pandas:

~~~
pandas.read_csv("data.csv", sep=";")
~~~

Na primeira coluna temos o dia da medição e na segunda a hora. Pandas possui uma
forma especial de lidar com datas e quando a data encontra-se dividido entre
colunas, como é o nosso caso, precisamos dar uma dica para o Pandas:

~~~
pandas.read_csv("data.csv", sep=";", parse_dates=[[0,1]])
~~~

Por último, se você estiver utilizando decimais no formato europeu (o mesmo
utilizado no Brasil) onde `,` é utilizado como separador é preciso utilizar [a
sugestão encontrada no stackoverflow](http://stackoverflow.com/a/11763490) para
que os números sejam interpretados corretamente.

~~~
pandas.read_csv("data.csv", sep=";", parse_dates=[[0,1]],
               converters={'chamber volume': lambda x: float(x.replace(',','.')),
                           'chamber area': lambda x: float(x.replace(',','.')),
                           'Air C T': lambda x: float(x.replace(',','.')),
                           'Pressure (atm)': lambda x: float(x.replace(',','.'))})
~~~

## Exercício
