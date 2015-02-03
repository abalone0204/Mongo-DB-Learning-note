#Lesson 2- Mongo DB simple introduction

## Pre-step

- `mongod` to open the mongoDB server.

- `mongo` to open the client for mongoDB.

- It's like a javascript console, actually, it is.

- `show dbs`: Show all the dbs in your computer

(Only MongoDB. You wouldn't like to see your mysql db appear here.)

- `mongoimport -d DIRNAME -c USER --file FILENAME` 

- `mongoexport -d DIRNAME -c USER --file FILENAME`

- `mongodump` create a binary export

- `mongorestore` restore a binary export

- `bsondump` converting binary data to json

- Quikly take a look what mongodb can do, if it's not so clear now, keep move on since knowing mongodb better would change the things you thought at first.

## BSON

- Short for **B**inary **JSON**. It's the way mongodb storing data.

## Driver

> An application communicates with MongoDB by way of a client library, called a `driver`.

- (http://docs.mongodb.org/manual/applications/drivers/)[http://docs.mongodb.org/manual/applications/drivers/]

