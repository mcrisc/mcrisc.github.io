---
layout: post
title:  "Instalando Atom no Ubuntu"
date:   2014-05-14 08:10:00
categories: ubuntu linux programming portuguese
---

[Atom](https://atom.io/) é o editor de textos *open source* lançado pelo [Github](https://github.com/). Por enquanto só há pacotes para Mac. Em sistemas Linux e Windows ainda é necessário compilá-lo a partir dos fontes. Aqui estão os passos para instalar o Atom no Ubuntu.

### Dependências

De acordo com [as instruções](https://github.com/atom/atom/blob/master/docs/build-instructions/linux.md) encontradas no repositório do projeto, para compilar o Atom é preciso ter:

- SO de 64 bits *(Ubuntu 64 bits, neste caso)*
- node.js v0.10.x
- npm v1.4.x
- libgnome-keyring-dev

Para instalar o o libgnome-keyring-dev:

```bash
sudo apt-get install libgnome-keyring-dev
```

Para instalar as versões mais recentes do node.js e do npm no Ubuntu, siga os passos abaixo (obtidos
[deste wiki](https://github.com/joyent/node/wiki/Installing-Node.js-via-package-manager#ubuntu-mint-elementary-os)):

```bash
sudo add-apt-repository ppa:chris-lea/node.js
sudo apt-get update
sudo apt-get install python-software-properties python g++ make nodejs
```

Por conta de um conflito de nomes, os pacotes do Ubuntu instalam um binário chamado `nodejs`, enquanto os scripts de compilação do Atom esperam encontrar um chamado `node`. Logo, será preciso criar um *link* simbólico:

```bash
cd /usr/bin
sudo ln -s nodejs node
```

Configure o npm:

```bash
npm config set python /usr/bin/python2 -g
```

### Gerando o Pacote

Execute os comandos abaixo -- conforme manda [a documentação](https://github.com/atom/atom/blob/master/docs/build-instructions/linux.md).

```bash
git clone https://github.com/atom/atom
cd atom
script/build # cria a aplicação em /tmp/atom-build/Atom
script/grunt mkdeb # gera um pacote .deb em /tmp/atom-build
```

Finalmente, instale o `.deb` que foi gerado em `/tmp/atom-build`:

```bash
dpkg -i /tmp/atom-build/atom-0.95.0-amd64.deb
```

E para carregar o editor, use:

````bash
atom
```

*Este material foi editado com o próprio Atom.*
