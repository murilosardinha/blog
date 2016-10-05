---
layout: post
title:  "Como começar com PhoneGap e WebSQL? (baby steps)"
categories: dev
author: murilosardinha
---

## Requisitos

* [Internet][Internet] - download/upload
* [PhoneGap Desktop app][PhoneGap-Desktop-app]
* [PhoneGap Developer app][PhoneGap-Developer-app] (opcional)
* [Google Chrome][Google-Chrome]

## Por onde começar?

* abrir o [PhoneGap Desktop app][PhoneGap-Desktop-app] e criar um novo projeto.
* conectar com o [PhoneGap Developer app][PhoneGap-Developer-app] caso tenha realizado o download.

## O que você pode fazer?

### Setando valores no html

Você pode setar o conteúdo do html do primeiro elemento onde a class do DOM é `<className>`. 
<br>
Por exemplo, se o nome da classe do DOM for `wrapper-text` você pode fazer o seguinte:

<script src="https://gist.github.com/murilosardinha/1b9e736fdad79e3f31759f41f3ddccf9.js"></script>

Então, se você tem um `<p class=“wrapper-text”>`, você pode setar o conteúdo desse <strong>p</strong>.

<script src="https://gist.github.com/murilosardinha/51ca9c0c2e3ef4d0f05e6b66ef9ffb84.js"></script>

O resultado será:

<script src="https://gist.github.com/murilosardinha/f6711b8a968e3b2ab94a9fd7b2f94e83.js"></script>

Mas, vamos fazer mais...

### Setando valores no html <strong>através do</strong> WebSQL db

Primeiro de tudo, temos que fazer uma conexão com o banco e tenha certeza de que você
está utilizando o <strong>[navegador Chrome][Google-Chrome]</strong>.

#### Conectando com o DB - Usando o WebSQL

O banco de dados WebSQL é um modelo que traz SQL para o lado do cliente (client side SQL).
Você precisará de algumas variáveis para iniciar o seu banco de dados:

1. o nome do banco;
2. o número da versão, pegue algo como ‘1.0’.
3. um texto de descrição;
4. e o tamanho do banco de dados em <strong>*kb</strong>.
* Logo, por exemplo, se você precisa de 1mb, use `1024 x 1024`, que dará 1mb.

Depois disso, você pode inicializar o seu Banco de dados em alguma variável.
<br>
Assim como o código abaixo, o db é inicializado em <strong>var db</strong>.

<script src="https://gist.github.com/murilosardinha/a199da1e920f367449e9281608efdf6d.js"></script>

A API de banco de dados Web SQL têm alguns métodos que você precisa saber.

1. openDatabase();
2. transaction();
3. executeSql();

Agora, você pode criar a sua primeira tabela.

1. você precisará de um nome para a tabela;
2. você irá utilizar o método `transaction()`;
3. isso gerarará um objeto transaction: `tx`;
4. depois disso, você pode rodar algum `sql`;
  * Para executar isso, tenha certeza que você setou alguns <strong>atributos</strong>
  na tabela como: `name, description, address, phone..`.

<script src="https://gist.github.com/murilosardinha/02351fdfdb9938657ff5f7c49509d4eb.js"></script>

E agora? Depois de ter criado a tabela, vamos inserir algum dado.

1. insira o atributo e o valor que irá ser setado em uma tabela específica;
2. não esqueça de usar a `variável db` e os métodos apresentados anteriormente;

<script src="https://gist.github.com/murilosardinha/1cf8ee06ba3723afc12dad05ed84e318.js"></script>

Agora, você está pronto para requisitar dados do db. Para fazer isso, nós
precisamos de um simples laço que tratará os resultados da query (rows).

<script src="https://gist.github.com/murilosardinha/a0cc0679486280d73f3b27b01471496f.js"></script>

## Compilar

Concluindo, você precisará:

1. compactar todo o seu projeto em um arquivo `.zip`;
2. faça upload para a <b>[plataforma do phonegap][phonegap-platform]</b>
3. escolha o tipo de projeto (público/privado):
* você poderá ter somente um projeto privado
4. e aguarde a compilação. 

Depois disso, você pode setar as chaves de desenvolvedor apple ou google se
você já tem. Caso contrário, você só poderá baixar o arquivo `.apk` para
dispositivos Android.

## O mais famosos frameworks e seus layouts

Se você não quer demorar muito codando o `.css` do projeto, você pode
simplesmente instalar o framework para trazer todo esse trabalho para você.
Eu recomendo alguns como:

* [ionic][ionic]
* [jQuery][jQuery]
* [bootstrap][bootstrap]
* [materialize][materialize]

[Internet]: download/upload
[PhoneGap-Desktop-app]: http://phonegap.com/getstarted/
[PhoneGap-Developer-app]: http://phonegap.com/getstarted/
[Google-Chrome]: https://www.google.com.br/chrome/browser/desktop/

[phonegap-platform]: https://build.phonegap.com/
[ionic]: http://ionicframework.com/docs/components/#card-images
[jQuery]: http://demos.jquerymobile.com/1.4.5/theme-default/
[bootstrap]: http://getbootstrap.com/components/#panels
[materialize]: http://materializecss.com/cards.html
