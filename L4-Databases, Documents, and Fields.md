#Lesson 4 - Databases, Documents, and fields

## First Step

- `sudo mongod` & `mongo` to opent the client.

- And you can see which database you're connecting.

- You can also type `db` to check it out.

- `show dbs`

- `use test`: connecting to database named `test` manually.

## Create database

- Simply type `use dennymarks`, you have a database named `dennymarks` right now.

- Inputing `db` on client, seeing the `dennymarks` is just like here, but it actually not. Run `show dbs` command, `dennymarks` had gone away.

- That's a liitle strange, but that's because mongodb won't create a database before you put some data in it,.

- Recap: `use DATABASE_NAME` can create a database although it won't be implemented before you put some real data inside.

## Create collection

- `db.links` would create collection named `links` for you.

- `db.links.count()` can see how many document in links now.

- Let's insert something in it.


## Create document

- `db.links.insert({title: "Denny Posts", url: "abalone0204@github.io", description: "I'm Denny, developer loveing programmin, eating, analyzing.", tags:["statistics", "murmurs", "web"], saved_on: new Date() });`

- You might say: "wow, I can put array inside it without creating another table?". Like Obama says, "Yes, you can!"

- Here's the cooler thing , remember the client is a javascript console? You can use instantly insert an object to MongoDB.

```javascript
{
    "meta" : {
        "OS" : "Mac OSX - Yosemite",
        "browser" : "Chrome"
    },
    "title" : "Denny's Blog",
    "url" : "http://abalone0204.github.io",
    "tags" : [
        "Tech",
        "Foods",
        "Rails",
        "Node.js"
    ],
    "descriptions" : "I'm Denny, developer loveing programmin, eating, analyzing.",
    "saved_on" : ISODate("2015-02-03T03:04:07.829Z")
}

```

- Instead using `insert`, we can use `save` which is the higher-level method. Since every document have its own **primary key** to prevent the duplex collections. So if there is first-time this collection been created, `save` will call `insert`, or it would use `update` method to update new data.

- If you put `save` and doesn't see errors, you success!

- To see is to believe, `db.links.find()` will show all of the documents in links. As you'll see, if we don't put query inside the find method, it'll show all the documents in links.

- `db.links.find().forEach(printjson)` is a built-in print out beutify function


```javascript
{
    "_id" : ObjectId("54d03bf85cf20f6ebb51abf5"),
    "meta" : {
        "OS" : "Mac OSX - Yosemite",
        "browser" : "Chrome"
    },
    "title" : "Denny's Blog",
    "url" : "http://abalone0204.github.io",
    "tags" : [
        "Tech",
        "Foods",
        "Rails",
        "Node.js"
    ],
    "descriptions" : "I'm Denny, developer loveing programmin, eating, analyzing.",
    "saved_on" : ISODate("2015-02-03T03:04:07.829Z")
}
```

- `ObjectId` is the topic next lesson will talk about.








































