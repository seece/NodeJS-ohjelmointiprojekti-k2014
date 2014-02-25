**Table of Contents**  *generated with [DocToc](http://doctoc.herokuapp.com/)*

- [Kivat moduulit](#kivat-moduulit)
	- [Web-frameworkit](#web-frameworkit)
		- [Express](#express)
		- [Koa](#koa)
		- [Geddy](#geddy)
		- [Restify](#restify)

# Kivat moduulit

Node.js projektina seuraa vahvasti unixin jalanjäljissä. Ideana on, että sovellukset koostuvat pienistä, uudelleenkäytettävistä moduuleista, joita yhdistelemällä saa aikaan helposti monimutkaisempia sovelluksia.

## Web-frameworkit

### Express

[Express](http://expressjs.com/) is a minimal and flexible node.js web application framework, providing a robust set of features for building single and multi-page, and hybrid web applications.

```javascript
var express = require('express');
var app = express();

app.get('/', function(req, res){
  res.send('hello world');
});

app.listen(3000);
```

### Koa

[Koa](http://koajs.com/) is a new web framework designed by the team behind Express, which aims to be a smaller, more expressive, and more robust foundation for web applications and APIs. Through leveraging generators Koa allows you to ditch callbacks and greatly increase error-handling.

```javascript
var koa = require('koa');
var app = module.exports = koa();

app.use(function *(){
  this.body = 'Hello World';
});

if (!module.parent) app.listen(3000);
```

### Geddy

[Geddy](http://geddyjs.org/) is a simple, structured web framework for Node. (Lue: Rails-klooni)

### Restify

[Restify](http://mcavage.me/node-restify/) is a node.js module built specifically to enable you to build correct REST web services. It intentionally borrows heavily from express as that is more or less the de facto API for writing web applications on top of node.js.

```javascript
var restify = require('restify');

function respond(req, res, next) {
  res.send('hello ' + req.params.name);
}

var server = restify.createServer();
server.get('/hello/:name', respond);
server.head('/hello/:name', respond);

server.listen(3000);
```