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

