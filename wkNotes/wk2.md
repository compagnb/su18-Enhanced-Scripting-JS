## Week 2
## Client Side Review & Node.js

### WHAT IS NODE.JS?
* Node.js is a JavaScript run-time environment, it includes everything you need to execute a program written in JavaScript.
* Node.js was created when JavaScript was extended from something you could only run in the browser to something you could run on your machine as a standalone application.


### WHAT IS NPM?
*  Node Package Manager
*  Provides two main functionalities:
    *  **Online repositories** for node.js packages/modules which are searchable on search.nodejs.org
    *  **Command line utility** to install Node.js packages, do version management and dependency management of Node.js packages.
* NPM helps javascript developers load dependencies effectively. To load dependencies we just have to run a command in command prompt:
```javascript

npm install

```
* This command is finding a **json** file named as package.json in root directory to install all dependencies defined in the file.

### Package.json

```json
{
  "name": "ApplicationName",
  "version": "0.0.1",
  "description": "Application Description",
  "main": "server.js",
  "scripts": {
    "start": "node server.js"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/npm/npm.git"
  },
  "dependencies": {
    "express": "~3.0.1",
    "sequelize":"latest",
    "q":"latest",
    "tedious":"latest",
    "angular":"latest",
    "angular-ui-router": "~0.2.11",
    "path":"latest",
    "dat-gui":"latest"
  }
}
```

* The **name** and **version** together form an identifier that is assumed to be completely unique. Changes to the package should come along with changes to the version. These are required, and the package won't install without them.
* NPM provide many useful Scripts like npm install, npm start, npm stop, etc.
* Some default script values are based on package contents, i.e. start command to node server.js.
* Dependencies are specified in a simple object that maps a package name to a version range. Version Name must be Version exactly.


### Node.js Allpication Break-down:
* **Import required modules** − Load Node.js modules.
* **Create server** − A server which will listen to client’s requests.
* **Read request and return response** − The server created in an earlier step will read the HTTP request made by the client which can be a browser or a console and return the response.

### Create a server.js
* First we need **http** to create an http server we use **require('http')** and pass it to a variable named http.
* Next, we need to defined **hostname** and **port number**, here we use **localHost** i.e **127.0.0.1** and **port number** **3000** and assign this to the variables hostname and port, respectively.
* Next, we create the http server using the **createServer** method.
    * This created the server as well as a response having **statusCode: 200, Content-Type header of plain text** and ends with the string **Hello World**. This is the response that the server can send to browser.
    * The function has two parameters **req** and **res** which is the **request** from and **response** to the server, respectively.
* As we created the server above , now it’s time to assign it a hostname and port number.
* Here, the server listens to localhost on port 3000 and prints “Server running at http://127.0.0.1:3000/ “ in command prompt.

``` JavaScript
/*server.js*/

const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer(function(req, res) {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, function() {
  console.log('Server running at http://'+ hostname + ':' + port + '/');
});
```

### Resources:
* Node.js website: [https://nodejs.org/en/](https://nodejs.org/en/)
* Node.js’ package ecosystem, or npm: [https://www.npmjs.com/](https://www.npmjs.com/)

### In-class Exercises/Challenges: 
    * Server Set-up
    * Hello World App
        

### VOCABULARY:
* Json
* Camelcase

### KEYWORDS:
* var 
* http
* createServer
* function
* writeHead
* \n
* listen
* process.env.PORT
* process.env.IP
* console.log
* require('http')
