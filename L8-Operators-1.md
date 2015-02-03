# Lesson 8 - Operator: The Basic Part

## The '$'

### Numerics

- To demonstrate the operator in mongodb, we then set an super easy and clear example below:

- `db.links.find({favourites: {$gt: 500}})` will get the links owning greater than 50 favourites.

- `$lt` : less than.

- `$lte` : less than and equal to (`<=`)

- `$gte` : greater and equal to (`>=`)

- And we can use `{favourites: { $gt: 100, $lte: 300}}` to set a range between 100 and 300. Holmes would said: "Elementary, my dear Watson."


### String

- `$in` : `db.users.find({'name.first': {$in:["John", "Bob"]}}).forEach(printjson)` 

```javascript
{
    "_id" : ObjectId("54d0a3c685c8080248674b65"),
    "name" : {
        "first" : "John",
        "last" : "Doe"
    },
    "age" : 30,
    "email" : "johndoe@gmail.com",
    "passwordHash" : "some_password_hash"
}
{
    "_id" : ObjectId("54d0a3c685c8080248674b67"),
    "name" : {
        "first" : "Bob",
        "last" : "Smith"
    },
    "age" : 31,
    "email" : "bob.smith@gmail.com",
    "passwordHash" : "last_password_hash"
}
```

- `$nin` : not in.

> `db.users.find({'name.first': {$nin:["John", "Bob"]}}).forEach(printjson)`

```javascript
{
    "_id" : ObjectId("54d0a3c685c8080248674b66"),
    "name" : {
        "first" : "Jane",
        "last" : "Wilson"
    },
    "age" : 25,
    "email" : "janewilson@gmail.com",
    "passwordHash" : "another_password_hash"
}
```

- `$all` : It's specially selector for a field which type is an array. Take a look at the example below.


> Example :
> - `db.links.find({tags: { $in: ['tutorials', 'screencasts']}}).forEach(printjson)`
 
```javascript
{
    "_id" : ObjectId("54d0a3c685c8080248674b68"),
    "title" : "Nettuts+",
    "url" : "http://net.tutsplus.com",
    "comment" : "Great site for web dev tutorials",
    "tags" : [
        "tutorials",
        "dev",
        "code"
    ],
    "favourites" : 100,
    "userId" : ObjectId("54d0a3c685c8080248674b65")
}
{
    "_id" : ObjectId("54d0a3c685c8080248674b69"),
    "title" : "Psdtuts+",
    "url" : "http://psd.tutsplus.com",
    "comment" : "Photoshop tutorials like none other",
    "tags" : [
        "photoshop",
        "tutorials"
    ],
    "favourites" : 507,
    "userId" : ObjectId("54d0a3c685c8080248674b66")
}
{
    "_id" : ObjectId("54d0a3c685c8080248674b6a"),
    "title" : "Tuts+ Premium",
    "url" : "http://tutsplus.com",
    "comment" : "The best screencast courses ever.",
    "tags" : [
        "screencasts",
        "tutorials"
    ],
    "favourites" : 149,
    "userId" : ObjectId("54d0a3c685c8080248674b65")
}
```

> But if we use `$all` instead
> `db.links.find({tags: { $all: ['tutorials', 'screencasts']}}).forEach(printjson)`

```javascript
{
    "_id" : ObjectId("54d0a3c685c8080248674b6a"),
    "title" : "Tuts+ Premium",
    "url" : "http://tutsplus.com",
    "comment" : "The best screencast courses ever.",
    "tags" : [
        "screencasts",
        "tutorials"
    ],
    "favourites" : 149,
    "userId" : ObjectId("54d0a3c685c8080248674b65")
}
```

- tip: You can thought `$all` and `$in` were `&` and `||` operator.(But we do have `and` and `or` selector in mongodb.)












