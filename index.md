---
layout: homepage
root: .
address: CBTE. Rua Giuseppe Máximo Scolfaro, 10.000 - Polo II de Alta Tecnologia - Campinas/SP.
country: Brazil
humandate: 28 de novembro de 2014
humantime: 14:00-17:00
startdate: 2014-11-28
enddate: 2014-11-28
latlng: -22.802888,-47.056702
registration: open
instructor: ["Raniere Silva"]
helper: ["Wanderson Luiz"]
---

## Informações Gerais

**Objetivos:**

-   Apresentar o IPython Notebook.
-   Apresentar a biblioteca Pandas.
-   Discutir workflow para trabalhar com análise de dados.

**Público alvo:** pesquisadores do CBTE.

**Onde**: {{ page.address }}.
{% if page.latlng %}
Direções podem ser obtidas no
[OpenStreetMap](//www.openstreetmap.org/?mlat={{ page.latlng | replace:',','&mlon=' }}&zoom=16)
ou
[Google Maps](//maps.google.com/maps?q={{ page.latlng }}).
{% endif %}

**Requisitos:**

-   Realizar a inscrição ([envie um email para
    {{site.contact}}](mailto:{{site.contact}}?subject=Inscrição Introdução a Pandas no CBTE&body=Gostaria de me participar do evento.))
-   Trazer seu notebook com alguns softwares instalados. **A lista dos
    softwares encontra-se [no fim dessa página](#configurao).**

Dúvidas devem ser encaminhadas por email para
[{{site.contact}}](mailto:{{site.contact}}).

<hr/>

## Cronograma

**Guias para cada um das partes encontram-se em [aqui](python/index.html).**

<table class="table table-striped">
<tr> <td>14:00</td> <td>Abertura</td> </tr>
<tr> <td>14:20</td> <td>IPython Notebook</td> </tr>
<tr> <td>15:00</td> <td>Intervalo</td> </tr>
<tr> <td>15:15</td> <td>Pandas</td> </tr>
<tr> <td>16:30</td> <td>Perguntas</td> </tr>
<tr> <td>16:50</td> <td>Encerramento</td> </tr>
</table>

<hr/>

## Configuração

Para participar dessa atividade, você vai precisar de
alguns programas instalados. Instruções para a instalação dos programas
encontram-se logo a baixo, separadas por sistema operacional. Por favor, tenha
certeza de ter instalado todos os programas.

### Windows

-   Baixe e instale [Anaconda CE](http://continuum.io/anacondace.html).
-   Utilize todas as opções padrões *exceto* por selecionar **Make
    Anaconda the default Python**.

### Mac OS X

-   Baixe e instale [Anaconda CE](http://continuum.io/anacondace.html).
-   Utilize todas as opções padrões *exceto* por selecionar **Make
    Anaconda the default Python**.

### Linux

Recomendamos o **all-in-one** instalador
[Anaconda](http://continuum.io/downloads.html).

1.  Baixe o instalador correspondente ao seu sistema operacional e salve
    no diretório do seu usuário.
2.  Abra um terminal.
3.  Digite

    ~~~
    $ bash Anaconda-
    ~~~

    e pressione `TAB`. O nome do arquivo que você baixou deve aparecer.

4.  Pressione enter. Siga as instruções que aparecerem no terminal.
    Quando aparecer dois pontos no fim da tela pressione a seta
    direcional para baixo até obter o fim do texto. Digite `yes` e
    pressione enter para aceitar a licença. Pressione enter para aceitar
    o diretório padrão para a instalação. Digite `yes` e pressione enter
    para adicionar Anaconda ao seu `PATH` (isso irá tornar Anaconda seu
    interpretador Python padrão).
