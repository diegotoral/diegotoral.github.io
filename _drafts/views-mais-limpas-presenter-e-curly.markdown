---
layout: post
title: Adeus ERB, bem vindo Curly!
---

Talvez você não concorde comigo, mas `ERB` **sucks**!!

Eu não gosto da sintaxe e muito menos de toda liberdade que a linguagem dá ao desenvolvedor. Como já dizia o tio Ben,

> Com grandes poderes vêm grandes responsabilidades.

Ter liberdade para "embutir" em suas views todo e qualquer trecho de código Ruby, mais cedo ou mais tarde, se torna um problema.

Em minhas pesquisas por alternativas ao `ERB`, terminei esbarrando com um projeto do pessoal do [Zendesk](https://www.zendesk.com/), o `Curly`, e gostei bastante.

## Curly
[Curly](https://github.com/zendesk/curly) é uma linguagem de templates para Ruby/Rails, que lembra bastante o [Handlebars](http://handlebarsjs.com/). No Curly, toda informação acessível para as views, deve ser "declarada" em classes, chamadas `presenters`.

`Presenters` são classes Ruby simples, que definem métodos, os quais ficam disponíveis para serem usados nas `views` da aplicação Rails.
Curly usa de convenções para determinar o presenter que deve ser usado, dependendo da `action` do controller executada na requisição, tornando realmente transparente o uso ou da gem.

Os arquivos de views devem ser terminados com a extensão `.curly` e cada view deve ser coberta por uma classe presenter, que ficam armazenadas no diretório `app/presenters`.

## Presenters
`Presenters` são classes de aprensentação, que vão armazenar toda, ou quase toda, a lógica de apresentação. Para quem está acostumado com o [Draper](), presenters podem ser comparados aos decorators.

## Views
<script src="https://gist.github.com/diegotoral/49393287918fa2cb0ad5.js"></script>

## Conclusões
