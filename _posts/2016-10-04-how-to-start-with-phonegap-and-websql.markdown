---
layout: post
title:  "How to start with PhoneGap and WebSQL? (baby steps)"
categories: dev
author: murilosardinha
---

## Requirements

* [Internet][Internet] - download/upload
* [PhoneGap Desktop app][PhoneGap-Desktop-app]
* [PhoneGap Developer app][PhoneGap-Developer-app] (optional)
* [Google Chrome][Google-Chrome]

## How to start?

* open the PhoneGap Desktop app and create a new project.
* connect to the PhoneGap Developer app.

## What you can do?

### Setting values to html

You can set the inner html of first element from document where its class name of DOM is `<className>`. 
<br>For example, if the class name of DOM is `wrapper-text` you can do the following:

<script src="https://gist.github.com/murilosardinha/1b9e736fdad79e3f31759f41f3ddccf9.js"></script>

So, if you have a `<p class=“wrapper-text”>`, you can set the content of this <strong>p</strong>.

<script src="https://gist.github.com/murilosardinha/51ca9c0c2e3ef4d0f05e6b66ef9ffb84.js"></script>

The result will be: 

<script src="https://gist.github.com/murilosardinha/f6711b8a968e3b2ab94a9fd7b2f94e83.js"></script>

But, let’s do more..

### Setting values to html <strong>from</strong> DataBase

First of all, let do a connection and be sure that you are at <strong>Chrome Browser</strong>.

#### Connection to DB - Using WebSQL

Web SQL Databases is a spec that brings SQL to the client side.
You will need some variables to set your database as:

1. the database name;
2. a version number, just pick one like ‘1.0’.
3. some text description;
4. and the size of database in *kb.
* So, for example, if you need 1mb, just put 1024 x 1024, that is 1mb.

After that, you can initialize your Database into a variable.
<br>As the code below, the db is initializing into <strong>var db</strong>.

<script src="https://gist.github.com/murilosardinha/a199da1e920f367449e9281608efdf6d.js"></script>

The Web SQL database API has some methods that you must know:

1. openDatabase();
2. transaction();
3. executeSql();

Now, you can create your first table.

1. you will need a table name;
2. you are going to use the method `transaction`;
3. it will get a transaction object: `tx`;
4. after that, you can run some `sql`;
  * To execute that, be sure to set some <strong>attributes</strong> to the table as: `name, description, address, phone..`.

<script src="https://gist.github.com/murilosardinha/02351fdfdb9938657ff5f7c49509d4eb.js"></script>

And now? After you've been created a table, let’s insert some data.

1. just insert the attribute and the value that is going to be setted to the specific table;
2. do not forget to use the db variable and the methods introduced above:

<script src="https://gist.github.com/murilosardinha/1cf8ee06ba3723afc12dad05ed84e318.js"></script>

Now, you are ready to request some data from db. To do that, we will need a simple loop for the result rows from query.


<script src="https://gist.github.com/murilosardinha/a0cc0679486280d73f3b27b01471496f.js"></script>

## Build

Finally, you must compact your whole project in a `.zip` format and upload to the [phonegap platform][phonegap-platform] and choose a private project and wait for the building. 
<br>After that, you can set the keys from apple or google developer account if you already have. If else, you can only download for your device the `.apk` for android.

## Most famous frameworks and its layouts

If you do not want to spend time coding the `.css`. You can install any framework to do the work for you. I can recommend some as:

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
