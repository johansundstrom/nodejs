# nodejs
Kom igång med Node.js och NPM

## NODE

* Node.js® är en JavaScript runtime och kommer ifrån Chrome's V8 JavaScript engine
* Skriven i C++
* Javascript som körs på server
* Node.js uses an event-driven, non-blocking I/O model that makes it lightweight and efficient. 
* Non-blocking - Single thread. Stjäl inte mycket CPU-tid
* Supportera >10 000 samtidiga anslutningar
* Node.js ekosystem av paket, npm, är det största open source biblioteken i världen
* Som asynkron event driven JavaScript runtime är Node designad för att bygga skalbara nätverksapplikationer

## Express
* Mest populära ramverket i Node.js
* Använder MVC
* Centrala begrepp är Middleware och Routing

## NPM
* Node package modules
* Hanterar versioner, installation och dependencies av paket
* https://www.npmjs.com/

## Guides

* https://nodejs.org/en/docs/guides/

## Installation

* https://nodejs.org/en/
* Node.js installerar även npm

#### Installation via terminal

```sudo apt install nodejs-legacy```

```sudo apt install npm``` //mac

## Versionskontroll

```javascript 
node --version //4.2.6
npm --version //3.5.2
```

#### Uppgradera till senaste
```sudo npm install npm@latest --global```
```sudo npm i --global npm```


#### eller...
```javascript
sudo npm cache clean -f
sudo npm install -g n
sudo n stable //n latest
```
#### Versionskontroll
```javascript 
node --version //9.6.1
npm --version //5.6.0
```

## Notera kommandoradsväxlar

* https://nodejs.org/dist/latest-v9.x/docs/api/

Command Line Options

## Installera ett paket

Vanliga paket
* Express - web server
* Mongo/Mongoose - koppling till MongoDB

```javascript
sudo npm install <package_name>
sudo npm install --global <package_name> //Installerar globalt 
```

## Avinstallera ett paket

```sudo npm uninstall <package_name>```

## Skapa projekt

* package.json - root
* dependencies - ^4.14.2

```npm init``` 

## REPL
* Node - REPL
* Read - Eval - Print - Loop

#### Testa gärna att utvärdera följande
```javascript
var d = new Date()
d
```

```javascript
for(var i = 0; i < 10; i++) {
    console.log(i);
}
```

```javascript
function hej(namn) {
    consle.log('Hej ' + namn);
}
hej('johan');
```

## Skapa Webbserver

* Skapa package.json
```javascript
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

## Installera Express

```javascript
npm install express --save //save to package.json
npm install body-parser --save
```
eller i package.json...
```javascript
"dependencies": {
    "express": "*", //latest
    "body-parser": "*"
},
```

kör sedan ```npm install```

i app.js skriver vi...

```javascript
var express = require('express');
var bodyParser = require('body-parser');
var path = require('path'); //core module

var app = express();

app.get('/', function(req, res){
    res.send('Hello');
})

app.listen(3000, function(){
    console.log('Server started');
});
``` 





