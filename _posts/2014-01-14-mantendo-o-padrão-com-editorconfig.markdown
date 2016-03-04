---
layout: post
title: Mantendo o padrão com EditorConfig
date: '2014-01-14 14:53:23'
---

Uma das coisas mais importantes quando se está trabalhando em equipe é manter o padrão. Todos os envolvidos em um projeto devem seguir o mesmo padrão. Em computação, isso significa, dentre outras coisas, remover espaços em branco no fim de cada linha, usar 2 ou 4 espaços para indentação, definir o encode dos arquivos, etc. O código do projeto deve ser um só, independente de quantas pessoas estejam trabalhando nele.

É comum perder algumas horas, e até mesmo dias, para configurar o ambiente de desenvolvimento, IDE, chaves ssh, banco de dados, etc (é um saco! falarei  mais sobre isso em outro post!). A configuração de IDE, em especial, é algo que geralmente fica esquecido ou é deixado de lado, pelo menos, até que os problemas comecem a surgir. As coisas ficam ainda piores, quando cada um da equipe passa a usar um editor diferente e até mesmo quando se trabalha em ambientes (PC e notebook, por exemplo) diferentes.

Para padronizar e automatizar a configuração de editores, temos o [EditorConfig](http://editorconfig.org/).

## EditorConfig

O EditorConfig é uma especificação e conjunto de plugins que permite descrever os estilos de codificação de um projeto.

Em poucos minutos (eu diria segundos) é possível definir todas as configurações desejadas, adicionar o arquivo de configurações `.editorconfig` ao projeto e ter todos os editores salvando código exatamente da mesma maneira.

O processo de instalação do plugin varia de uma IDE para outra, mas geralmente é bem simples. Você pode encontrar o plugin para seu editor predileto [aqui](http://editorconfig.org/#download). Siga as instruções de instalação e pronto.

A sintaxe do arquivo de configurações é muito simples, não existe muito o que comentar. Acredito que qualquer um seja capaz de compreender o trecho abaixo:

```
[*.py]
indent_style = space
indent_size = 4
```

Existem alguns outros parâmetros que podem ser configurados, a lista completa encontra-se na [wiki do projeto](https://github.com/editorconfig/editorconfig/wiki/EditorConfig-Properties). É importante resaltar, que algumas opções podem não estar disponíveis para determinados plugins, então fique atento.

Também é possível especificar diversas configurações dentro de um mesmo projeto. Para isto, basta criar vários arquivos `.editorconfig`, um em cada diretório do projeto onde as configurações devem ser diferentes.

Versione o arquivo `.editorconfig` junto com os arquivos do seu projeto, assim todos terão acesso as configurações, além de ficar fácil manter alterações no arquivo.