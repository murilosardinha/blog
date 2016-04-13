---
layout: post
title:  "Desenvolvendo aplicativos móveis em tempos de HTML5"
categories: dev
author: murilosardinha
---

Cordova é uma ótima ferramente para prototipação rápida. Ou seja, se seu aplicativo não necessita de alto desempenho de hardware,
você está apto para utilizar ferrametas de desenvolvimento de aplicativos híbridos.

A grande vantagem de um híbrido é codar ao mesmo tempo* um aplicativo para Android, iOS e Windows Phone.
Mas nem tudo são flores.

> ao mesmo tempo* = Em casos específicos de utilização de plugins (google Maps, camera, splash screen ..)
você terá que adaptar as diferentes chamadas de recursos no código para cada plataforma.<br>
Porém, codar 10% para cada plataforma é melhor que 100% para cada uma delas.

## Cordova:
Criar aplicativos utilizando HTML, CSS e JS
para multiplas plataformas agora virou brincadeira de criança.

O Cordova utiliza Node.js e está disponível para o gerenciamento de multiplas plataformas através do npm.

## Primeiros Passos:

### **Instalação**
1. Abra o terminal ou o command prompt e execute `$ npm install -g cordova`.

### **Configurando o Ambiente**
1. Para as diferentes plataformas, siga suas respectivas [set up's de ambiente][setup-environment]
* [android][android]
* [iOS][ios]
* [Windows Phone][windows-phone]
* [outras][others]

## Criando Meu Primeiro App:
 1. `$ cordova create <path> <id> <app_name>`
  * path: nome do diretório
  * id: domínio do app ao contrário. Ex: `com.example.hello`
  * app_name: nome do app
 2. Adicionando uma plataforma.
  * `$ cordova platform`, para verificar plataformas disponíveis.
  * `$ cordova platform add <platform name>`
  * `$ cordova run <platform name>`, para rodar seu projeto.
  * `$ cordova serve`. Para rodar seu projeto no navegador.

> Hint: Para toda alteração no código, repita o item 4 ou 5. <br>
Para resolver este “problema”, execute através do [phonegap*][phonegap]: `$ phonegap serve`.

## Criando o App do DevInSanta (Baby steps):

### Index.html

* eu precisei comentar esta linha dentro do `<head>`

{% gist 14bd0cd4c2c17bed2ee6781678724126 header.html %}

* insira dentro do `<body>`

{% gist 1b57803e132203dccb10bef167c6a415 index.html %}

## Comparando Resultados
O app deve buscar todos os posts publicados no blog, bem como o título,
descrição e o link para a página do post.

A brincadeira tem o intuito de incentivar e fomentar a criatividade, além de mostrar a
quantidade de possibilidades que um app com a simples função de buscar o arquivo `.xml` ou `.json` de um site,
por exemplo, pode fazer.

## Contribua Na Nossa Comunidade
Continue o app e compartilhe sua experiência com apps híbridos.
Acesse [github.com/DevInSanta][DevInSanta] para mais informações.<br>

Não sabe como compilar um app híbrido usando o Cordova?<br>
Deixe seu comentário ou [sugira em um novo post][suggestions].<br>


[setup-environment]: http://cordova.apache.org/docs/en/latest/guide/platforms/

[android]: http://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html
[ios]: http://cordova.apache.org/docs/en/latest/guide/platforms/ios/index.html
[windows-phone]: http://cordova.apache.org/docs/en/latest/guide/platforms/wp8/index.html
[others]: http://cordova.apache.org/docs/en/latest/guide/platforms/

[phonegap]: http://www.lucianotamanaha.com/design/qual-a-diferenca-entre-phonegap-e-cordova/
[DevInSanta]: https://github.com/DevInSanta/blog
[suggestions]: https://github.com/devinsanta/blog/issues
