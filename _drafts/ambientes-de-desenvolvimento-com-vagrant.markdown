---
layout: post
title: Ambientes de desenvolvimento com Vagrant
---

Se você é um desenvolvedor, já passou pelo sufoco de configurar todo o ambiente de desenvolvimento algumas vezes. Basta formatar sua máquina ou adicionar um novo integrante ao projeto e lá se vão algumas horas. Instalar inúmeras bibliotecas, gerenciadores de pacotes, servidor web, banco de dados, Git, etc, é um inferno, mas não precisa ser assim sempre.

Boa parte desse trabalho pode ser minimizado, ou até mesmo eliminado, com o uso de máquinas virtuais, onde todo o ambiente de desenvolvimento pode ser configurado e, posteriormente, compartilhado, reutilizado e até mesmo, versionado.

Existem algumas poucas maneiras de alcançar este objetivo, mas neste post trataremos da mais difundida delas, o Vagrant.

## Vagrant?
Segundo a definição disponível na documentação oficial:

> Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize the productivity and flexibility of you and your team.

Em outras ~~nas minhas~~ palavras, Vagrant é um programa de linha de comando, open source, escrito em Ruby, que permite *iniciar*, *reiniciar*, *provisionar* e *acessar via ssh* uma determinada box (VM), seguindo configurações em um arquivo *Vagrantfile*.

Vagrant oferece suporte a diferentes *providers*, como o VirtualBox, VMware e até mesmo AWS e DigitalOcean.

## Instalação
Para informações sobre o processo de instalação do Vagrant, consulte a [documentação](http://docs.vagrantup.com/v2/installation/index.html) oficial.

## Vagrantfile
O `Vagrantfile` é o arquivo de configuração do Vagrant. Todos os parâmetros deste arquivo são escritos em Ruby, mas não se preocupe se você não sabe Ruby, pois é realmente muito simples alterar as opções contidas neste aquivo.

Este arquivo concentra configurações da  máquina virtual, como configurações de rede, mapeamento de portas (da máquina virtual para o host) e opções de provisionamento (mais detalhes em um instante).

O Vagrant dispinibiliza um comando para criar tal arquivo.
```
$ vagrant init
```

O `Vagrantfile` gerado, contém configurações *default* e deve se parecer com a versão simplificada exposta abaixo:
```
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "base"
end
```

## ABC do Vagrant
Vagrant torna realmente simples trabalhar com máquinas virtuais. Todo o processo é realizado pela linha de comando (viva!) e se resume aos comandos `up`, `halt`, `status`, `reload` e `ssh`.

Para inicializar uma máquina, basta pedir ao Vagrant:
```
$ vagrant up
```

O Vagrant irá procurar no diretório atual um arquivo `Vagrantfile` e, caso encontre, utilizará as configurações disponíveis nele para criar a máquina virtual. Caso o arquivo não exista, uma mensagem de erro será exibida.

```
$ vagrant up
A Vagrant environment or target machine is required to run this
command. Run `vagrant init` to create a new Vagrant environment. Or,
get an ID of a target machine from `vagrant global-status` to run
this command on. A final option is to change to a directory with a
Vagrantfile and to try again.
```

Uma vez que a máquina está devidamente inicializada, o comando `halt` pode ser usado para desligá-la.

```
$ vagrant halt
```

Vagrant oferece um comando para exibir o `status` da máquina virtual.

```
$ vagrant status
```

Para acessar via `ssh` a máquina virtual vagrant use o comando:
```
$ vagrant ssh
```

Se tudo correr bem, você terá acesso root à máquina.

## Provisionamento
Vagrant oferece algumas opções de provisionamento das máquinas virtuais que gera - Chef, Puppet e Shell.

Para os casos mais simples, um shell script é mais do que suficiente para realizar a configuração completa do ambiente de desenvolvimento. Esta também é a opção mais indicada, se você deseja iniciar rapidamente um ambiente virtual.

## Conclusões
Vagrant é uma ferramenta extremamente útil e que realmente facilita e agiliza o `workflow` com máquinas virtuais, no entanto, dada a natureza "consumidora" de recursos das VMs, existirão situações onde utilizá-las será impossível.