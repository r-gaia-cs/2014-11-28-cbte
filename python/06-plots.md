---
layout: lesson
root: ..
title: Visualizando dados
---

## Objetivos

- Criar algumas visualizações

## Exemplo

No IPython Notebook, para visualizar os gráficos no próprio caderno de anotações
é preciso criar uma célula contento

~~~
%matplotlib inline
~~~

e executá-la. **Recomenda-se que essa seja a primeira célula.**

Para criar um gráfico com **todas** as informações da nossa tabela utilizamos

~~~
meus_dados.plot()
~~~

Infelizmente, dado a grande quantidade de informação não podemos concluir nada
pelo gráfico anterior. Para obtermos um gráfico com informações mais uteis
precisamos primeiro filtrar nossa tabela e depois utilizar o método `plot()`.

Queremos visualizar os dados relacionados com

- "Chamber" igual a 1 **e**
- "Treatment" igual a "Sem palha" **e**
- "sampling time" igual a 15.

Primeiro precisamos filtrar nossa tabela com relação aos dados anteriores:

~~~
meus_dados_filtrados = meus_dados[(meus_dados['Chamber'] == 1) & (meus_dados['Treatment'] == 'Sem palha') & (meus_dados['sampling time'] == 15)]
~~~

Antes de avançar, podemos dar uma olhada na tabela resultante do nosso filtro:

~~~
meus_dados_filtrados
~~~

Vamos visualizar o "Air C T":

~~~
meus_dados_filtrados['Air C T'].plot()
~~~

Se dermos uma olhada no eixo horizontal temos que os valores estão estranhos.
Eles estão estranhos porque Pandas está utilizando o ID (ou número da linha).

O método `plot()` aceita dois argumentos chamados de `x` e `y` que corresponde
a coluna a ser utilizada para o eixo horizontal e vertical, respectivamente.
Utilizando esses argumentos podemo refazer o gráfico anterior utilizando:

~~~
meus_dados_filtrados.plot(x=0, y='Air C T')
~~~

Podemos adicionar algumas informações no nosso gráfico como, por exemplo,
legenda nos eixos. Para isso utilizamos os métodos `set_*()`:

~~~
minha_visualização = meus_dados_filtrados.plot(x=0, y='Air C T', title="Visualização do Air C T", legend=False, grid=True)
minha_visualização.set_xlabel('Date')
minha_visualização.set_ylabel('Air C T')
~~~

Além dos argumentos `x`, `y`, `title`, `legend`, `grid` o método `plot()` possui
um argumento `kind` relacionado com o tipo de gráfico a ser criado. Por padrão
`kind` é igual a `line` mas ele também pode ser `bar`, `barh`, `hist`, `box`,
`kde` `density`, `area`, `pie`, `scatter`, `hexbin`. Podemos refazer o gráfico
anterior como um gráfico de barras utilizando:

~~~
minha_visualização = meus_dados_filtrados.plot(x=0, y='Air C T', kind='bar', title="Visualização do Air C T", legend=False)
minha_visualização.set_xlabel('Date')
minha_visualização.set_ylabel('Air C T')
~~~

O argumento `y` do método `plot()` aceita uma lista com as colunas desejadas.
Para vizualizar o "Air CT" e o "K T":

~~~
meus_dados_filtrados.plot(x=0, y=['Air C T', 'K T'], title="Visualização do Air C T e K T")
~~~

A ordem de magnitude dos valores das colunas é diferente a visualização fica
comprometida. Uma alternativa é utilizar dois eixos verticais (um na esquerda e
outro na direita). Informamos as colunas que iram utilizar o eixo vertical da
direita utilizando o arquivos `secondary_y`:

~~~
meus_dados_filtrados.plot(x=0, y=['Air C T', 'K T'], secondary_y=['K T'], title="Visualização do Air C T e K T")
~~~

Também podemos adicionar algumas informações no nosso gráfico.

~~~
minha_visualização = meus_dados_filtrados.plot(x=0, y=['Air C T', 'K T'], secondary_y=['K T'], title="Visualização do Air C T e K T", grid=True)
minha_visualização.set_xlabel('Date')
minha_visualização.set_ylabel('Air C T')
minha_visualização.right_ax.set_ylabel('K T')
~~~

E podemos refazer o gráfico anterior como um gráfico de barras:

~~~
minha_visualização = meus_dados_filtrados.plot(x=0, y=['Air C T', 'K T'], secondary_y=['K T'], kind='bar', title="Visualização do Air C T e K T", grid=True)
minha_visualização.set_xlabel('Date')
minha_visualização.set_ylabel('Air C T')
minha_visualização.right_ax.set_ylabel('K T')
~~~

## Exercício

1. Tente criar outros gráficos utilizando outros filtros.
