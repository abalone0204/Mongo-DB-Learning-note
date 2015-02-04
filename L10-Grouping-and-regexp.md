#Lesson 10 - Grouping and Regex

## Distinct

- `distinct('FIELD_NAME')` : Can only get all field's distinct value we want.

## Grouping data

- Now we want to do some more complicated.

### Example

> We want to select each user's name with his or her links' favourites count.

```javascript

db.links.group({ 
    key: { userId: true},
    initial: { favCount: 0},
    reduce: function(doc, o){
        o.favCount += doc.favourites;
    },
    finalize: function(o){
        o.name = db.users.findOne({_id: o.userId}).name;
    }
})

```
- Now we chekc these code step by step.

- `key`: It's what you want the data group based on. `key:{ userId: true}` means that we want to group data based on userId.

- `initial`: We set initial value to our result document

- `reduce`:  This function will run on each document. The first argument is original document, the second is the result.

- `finalize` : each document which grouped by `key` will run the `finalize` after they've completed `reduce`.

- But you'll encounter an error, since mongo won't let you use shared collection in `group()`, check the doc [here](http://docs.mongodb.org/manual/reference/command/group/).


```javascript
finalize: function(o){
        o.name = db.users.findOne({_id: o.userId}).name;
    }
```


`key, reduce, initial [, keyf] [, cond] [, finalize] }`


## Regular Expression

- Simple way: `db.links.find(url: /.com$/)`

- Or you can use `$regex` operator. `db.links.find(url:{$regex:{ /.com$/}})`.

> Why do this is because you can combine `$regex` with other operator to implement much more complex query
> `db.links.find({url: {$regex: /.com$/, $ne: "http://www.audible.com"}, title: {$ne: "Nettuts+"}},{title: 1, url: 1,_id:0})`



