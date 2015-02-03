#Lesson 7 - Query

## Before started

- Those data are created by tutsplus, you can visit their web-site, there are so many nice courses there.

- [link](https://code.tutsplus.com)

## How to import data?

- `mongo 127.0.0.1/bookmarks data/bookmarks.js`

- `127.0.0.1` : localhost.

- `/bookmarks` let mongodb know you're going to using the `bookmarks` database

- `data/bookmark.js` tell computer to run all the code in this file.

- Then you can run `mongo bookmarks` to connect the database.

## Let's Query!

### Get all things

- `db.users.find()`: likes SELECT * FROM USERS.

- Just a small tip, everything you query out were array, you can use `.forEach(printjson)` to get a better format.

### Get all thing more specificly

- You can treat query in mongo db as an object, just put it into the `find()`

> Example:
> `db.users.find({ age: 31})`

- And finding something in an array column is as simple as we usually do.

> Example:
> run `db.links.find({tags: 'marketplace'})`
> Notice that every tags column is an array, and no one is a string:'marketplace', but mongodb smart enoungh to handle this for us.

- `.findOne()` is work like `find()` but it return an object, not an array.

### Select specific fields

- The second argument in the `find()` method, you can set a selection filter to get the specific filed you want.

> Example
>
> `db.users.findOne({'name.first':'Bob'}, {email: 1})` or `db.users.findOne({'name.first':'Bob'}, {email: true})`
> Then we only retrieve the `email` and `_id` fields.

- But if we can't use the selection objec mix with 1 and 0, like `{email: 1, title: 0}` except the `_id` field since it's true by default.

