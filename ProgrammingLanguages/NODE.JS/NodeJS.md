# LEARNING NOTES
## Initial Setup
- In a folder create a file with a ```.js``` path.
- Run it in the terminal with ```node [filename]``` or ```nodemon [filename]``` 
- Make sure to get package.json by running ```npm init``` in the terminal.
>Ensure node_modules file is in .gitignore. For others to run the program, they can write ```npm install``` in the terminal to download all the dependencies.

## Express
- Express is a framework that allows you to write cleaner and readable code on the server side.
- Do ```npm install express``` on your backend.

## The Global Object
- In Node.JS, the global object is what contains some methods, such as ```setTimeout(), setInterval()```
- ```__dirname``` gets us the absolute path of the folder WITHOUT the file name.
- ```__filename``` gets us the absolute path of the folder WITH the file name.

## Modules and Require
- It's better to place in your code in different files to keep code modular and reusable.
- To import from a file, use ```const [variableName] = require([filename])```
- To export a variable from a file, use ```module_exports = [variableName or value]```
- You can also access Node's in-built core modules such as ```const os = require('os')```

## File System (can only be done in NodeJS)
- Import the module with ```const fs = require('fs');```
- Read files: ```fs.readFile('[filename]', (err, data) => {})```
- Write to files: fs.writeFile('[filename]', '[text]', () => {})
- To make a directory/folder: ```fs.mkdir('[dirname]', (err) => {})```
- To remove a directory/folder: ```fs.rmdir('[dirname]' )
- To check if a file exists: ```fs.existsSync('[filename or dirname]')``` 
- To delete a file: ```fs.unlink('[filename]', (err) => {})```

## Buffers and Streams
- Sometimes if you need to read from a large file use ```const readStream = fs.createReadStream('[filename]')```
    - Then use ```readStream.on('data', (chunk) => {})```
- Similarly, to write large chunks of data to a file ```const writeStream = fs.createWriteStream('[filename]')```
    - Then use ```writeStream.write(chunk)```

## Servers and Clients 
- A client sends a request to the server and the server responds.
- To create a server (without express.js) export the ```const http = require('http');```
    - Create server with ```const server = http.createServer((req, res) => {})
    - Make sure the server listens for requests with ```server.listen([PortNumber], '[localhost or frontend url]')```

## Middleware
- A piece of code that runs on the server between getting a request and sending a response (Web Middleware).
>```app.use(func)``` is a middleware that will run for every type of request and route.
>```app.get('/', func)``` will only run when a GET request is sent.
- Middleware Examples
    - Logger middleware to log details of every request.
    - Authentication check middleware for protected routes.
    - Middleware to parse JSON data from requests.
    - Return 404 pages.

