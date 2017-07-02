# Install-nodejs
### How to install nodejs on ubuntu 16.04 LTS


Node.js is available in two versions, first is current (most recent version) and another is LTS. Select which version you need to install on the system. Then use one of following commands to install PPA on your system. Node.js officially provides these PPA’s.

- **Step 1:install PPA on your system**
Use Current Release:  Node.js 8.0 is the current Node.js release available.
```
$ sudo apt-get install python-software-properties
$ curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
```
Use LTS Release : Node.js 6.11 is the LTS release available.
```
$ sudo apt-get install python-software-properties
$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
```
For this tutorials, we are using latest current release and added their PPA to my system.
- **Step 2: Install Nodejs and NPM**

After adding required PPA file lets install Node package. NPM will also be installed with node.js. This command will also install many other dependent packages on your system.
```
$ sudo apt-get install nodejs
```
- **Step 3: Check Node.js and NPM Version**

After installing node.js verify and check the installed version. You can find more details about current version on node.js official website.
```
$ node -v 

v8.0.0
```
Also, check the version of installed npm.
```
$ npm -v 

5.0.0
```
- **Step 4: Create Demo Web Server (Optional)**

This is an optional step. If you want to test your node.js install. Let’s create a web server with “Hello World!” text. Create a file http_server.js
```
$ vim http_server.js
```
and add following content
```
var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World\n');
}).listen(3000, "127.0.0.1");
console.log('Server running at http://127.0.0.1:3000/');
```
Now start the Node application using below command.
```
$ node http_server.js

debugger listening on port 5858
Server running at http://127.0.0.1:3000/
```
You can also start the application with debugging enabled with the following commands.
```
$ node --inspect http_server.js

Debugger listening on ws://127.0.0.1:9229/8976a32b-cf99-457c-85fb-e7288cbadac6
For help see https://nodejs.org/en/docs/inspector
Server running at http://127.0.0.1:3000/
```
The web server has been started on port 3000. Now access http://127.0.0.1:3000/ URL in browser. Now you will need to configure a front-end server for your app. 
