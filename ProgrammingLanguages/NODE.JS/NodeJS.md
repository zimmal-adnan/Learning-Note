# LEARNING NOTES
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
