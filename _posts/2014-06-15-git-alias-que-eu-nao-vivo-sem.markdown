---
layout: post
title: Git alias que eu não vivo sem
date: '2014-06-15 16:28:53'
---

O git faz parte do meu dia-a-dia e de muitos outros desenvolvedores. É uma das ferramentas mais importantes do ambiente de densevolvimento e fundamental para se trabalhar em equipe.

O git faz milagres, mas realizar algumas tarefas, inúmeras vezes ao dia, pode ser realmente muito cansativo. Para facilitar a nossa vida, git oferece a possibilidade de definir `alias` para comandos que o usuários desejar.

Abaixo estão os principais alias que tenho registrados e que uso no meu dia-a-dia.

## $ git  st
Sem dúvida, o melhor e mais usado alias da minha coleção. É impossível ficar muito tempo sem verificar as alterações que fiz ou os arquivos que selecionei para commit. Este alias me salva da tarefa entediante de digitar `status` sempre que preciso verificar as alterações que fiz.

```sh
$ git config --global alias.st status
```

## $ git ci
Depois do `status`, `commit` deve ser o comando mais usado. Este alias simples, me permite economizar na quantidade de texto que digito para fazer meus commits.

```sh
$ git config --global alias.ci commit
```

## $ git co
Se você trabalha com git da "maneira correta", ou segue algum workflow como o [git-flow](http://nvie.com/posts/a-successful-git-branching-model/), mudar de `branch` é uma tarefa bastante corriqueira, por isso, considero este um dos principais alias da minha pequena coleção (o autocompletar não ajuda com o `checkout`).

```sh
$ git config --global alias.co checkout
```

## $ git uncommit
Todos nós erramos! É bastante comum commitar um arquivo que não deveria ser commitado ou perceber algum erro de digitação na mensagem de commit, logo após ter feito o bendito commit. Bem, para isso, eu criei o alias `uncommit`. Tem sido meu salvador desde então.

```sh
$ git config --global alias.uncommit 'reset --soft HEAD^'
```

## $ git unstage
Esse é outro comando salvador. Quando você adiciona um arquivo que não deveria, é com o `unstage` que você pode contar!

```sh
$ git config --global alias.unstage 'reset HEAD --'
```

## $ git last
Exibir o último commit realizado agora ficou fácil!

```sh
$ git config --global alias.last 'log -1 HEAD'
```

Você pode criar alias para qualquer comando que desejar, é uma boa prática e no fim das contas, vai te poupar muito tempo.