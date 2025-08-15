# LEARNING NOTES
## What is MongoDB?
- MongoDB is a NoSQL database that stores records of data in collections and documents.
    - Each collection contains documents. 
    - Each document contains a single item of data.
    - Records are stored in key-value pairs in a JSON style.

## Setup
- Go to [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
- Make a collection.
- Create a user for reading/writing to database.
    - Go to Database Access.
    - Give read/write access.
    - Now only the valid user can conenct to the database.
- Click on Connect and choose "MongoDB for VS Code"
- In VS Code, write ```const dbURI = [ConnectionString]```
- Replace username and password with the new user you just made.
- Add the collection name at the end of the URI.

## Mongoose
- Wraps the MongoDB API and provides an easier way to connect to and interact with the MongoDB database
- Can create Data models which have database query methods to create, delete, save and get database documents.
- To work with Mongoose:
    - Create a new folder and call it "models"
    - Inside it name a file ```[collectionName].js```
    - Add ```const mongoose = require("mongoose");``` and ```const Schema = mongoose.Schema;``` at the top.
    - Create a new schema. 
        - Schemas define the structure of the type of data (String, Date, Boolean...) and whether it is required.
    - You create a model based on that schema with ```const [modelName] = mongoose.model("modelName", [schemaName]);```
        - The model can help the program communicate with the database
- Make sure to use ```mongoose.connect(dbURI)``` on the server code
