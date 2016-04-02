---
layout: post
title:  "Desenvolvendo aplicativos em tempos de HTML5"
categories: dev
author: murilosardinha
---

Se seu aplicativo não necessita de alto desempenho de hardware,
você acaba de preencher o primeiro requisito para utilizar ferrametas de desenvolvimento de aplicativos híbridos,
na minha humilde opinião.

A grande vantagem de um híbrido é codar ao mesmo tempo* um aplicativo para Android, iOS e Windows Phone.
Mas nem tudo são flores.

> ao mesmo tempo* = Em casos específicos de utilização de plugins (google Maps, camera, splash screen ..)
você terá que adaptar as diferentes chamadas de recursos no código para cada plataforma.<br>
Porém, codar 10% para cada plataforma é melhor que 100% para cada uma delas.

## Cordova:
Apresento-lhes o Apache Cordova. Criar aplicativos utilizando HTML, CSS e JS
para multiplas plataformas agora virou brincadeira de criança.

O Cordova utiliza Node.js e está disponível para o gerenciamento de multiplas plataformas através do npm.

## Primeiros Passos:
1. Abra o terminal ou o command prompt e execute `$ npm install -g cordova`.
2. Para as diferentes plataformas, siga suas respectivas [set up's de ambiente][setup-environment]
3. Pronto!

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

  1. insira dentro do <body>

    {% highlight html %}
    <body>
      <div id="demo"><br><br></div>

      <script>
        // o blog disponibiliza um feed .xml
        // realizando e preparando o request via 'pure javascript'
        var xhttp = new XMLHttpRequest();
        xhttp.onreadystatechange = function() {
          if (xhttp.readyState == 4 && xhttp.status == 200) {
            // status == 200, executa a função.
            myFunction(xhttp);
          }
        };
        xhttp.open("GET", "http://devinsanta.github.io/blog/feed.xml", true);
        xhttp.send();

        function myFunction(xml) {
          // tratando os dados
          var xmlDoc = xml.responseXML;
          var items  = xmlDoc.getElementsByTagName('item');

          // para cada item encontrado através da tag <item>
          for(var i = 0; i < items.length; i++){
            var title       = items[i].getElementsByTagName('title')[0];
            var description = items[i].getElementsByTagName('description')[0];
            var url         = items[i].getElementsByTagName('link')[0];

            // renderizando no elemento de id == "demo"
            // limitando o N de char da variavel `description`
            document.getElementById("demo").innerHTML +=
              "<a href='http://devinsanta.github.io" + url.textContent + "'>" +
              title.textContent + "</a> <br>" +
              description.textContent.substring(0,100) + "...<br><br>";
          }
        }
      </body>
    </script>
  {% endhighlight %}


## Contribua Na Nossa Comunidade
Continue o app e compartilhe sua experiência com apps híbridos.
Acesse [github.com/DevInSanta][DevInSanta] para mais informações.


[setup-environment]: http://cordova.apache.org/docs/en/latest/guide/platforms/
[phonegap]: http://www.lucianotamanaha.com/design/qual-a-diferenca-entre-phonegap-e-cordova/
[DevInSanta]: https://github.com/DevInSanta/blog
