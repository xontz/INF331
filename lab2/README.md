## Tarefa sobre catálogo de componentes

> [Link para Notebook](notebook/components-01-catalog.ipynb)

## Tarefa Web Components 1

~~~html
<dcc-trigger label="Mundo"
             action="noticia/mundo/politica"
             value="Trump has gone mad!!">
</dcc-trigger>

<dcc-trigger label="Brasil P"
             action="noticia/brasil/politica"
             value="Bolsonaro tenta oferecer cloroquina para Ema, que por ser mais inteligente que ele, sai correndo.">
</dcc-trigger>

<dcc-trigger label="Brasil E"
             action="noticia/brasil/esporte"
             value="Cruzeiro tenta, mas continua na segunda divisão">
</dcc-trigger>

<dcc-trigger label="Bahia"
             action="noticia/bahia/esporte"
             value="Jogadores do Bahia dizem preferir ficar na rede do que voltar aos campos após quarentena.">
</dcc-trigger>

<dcc-lively-talk duration="0s"
                 character="doctor"
                 speech="">
  <subscribe-dcc topic="#/politica"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0s"
                 character="nurse"
                 speech="">
  <subscribe-dcc topic="noticia/b#"></subscribe-dcc>
</dcc-lively-talk>

<dcc-lively-talk duration="0s"
                 character="patient"
                 speech="">
  <subscribe-dcc topic="noticia/#"></subscribe-dcc>
</dcc-lively-talk>
~~~

## Tarefa Web Components 2


~~~html
<dcc-trigger label="Next Item" action="next/rss">
</dcc-trigger>

<dcc-rss publish="rss/science" source="https://www.wired.com/category/science/feed">
  <subscribe-dcc topic="next/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-rss publish="rss/design" source="https://www.wired.com/category/design/feed">
  <subscribe-dcc topic="next/rss" role="step"></subscribe-dcc>
</dcc-rss>

<dcc-aggregator publish="aggregate/science" quantity="5">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-aggregator>

<dcc-lively-talk id="doctor"
                 duration="0s"
                 character="doctor"
                 speech="">
  <subscribe-dcc topic="aggregate/science"></subscribe-dcc>
</dcc-lively-talk>
<dcc-lively-talk id="nurse"
                 duration="0s"
                 character="nurse"
                 speech="">
  <subscribe-dcc topic="rss/science"></subscribe-dcc>
</dcc-lively-talk>
<dcc-lively-talk id="patient"
                 duration="0s"
                 character="patient"
                 speech="">
  <subscribe-dcc topic="rss/design"></subscribe-dcc>
</dcc-lively-talk>
~~~