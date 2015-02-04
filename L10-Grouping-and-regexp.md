#Lesson 10 - Grouping and Regex

## Distinct

- `distinct('FIELD_NAME')` : Can only get all field's distinct value we want.

## Grouping data

- Now we want to do some more complicated.

### Example

> We want to select each user's name with his or her links' favourites count.

```javascript

db.links.group({ 
    key:{ userId: true},
    initial: { favCount: 0},
    reduce: function(doc, i){
        o.favCount += doc.favourites;
    },
    finalize: function(o){
        o.name = db.users.findOne({_id: o.userId}).name;
    }
})


```


## Regular Expression

- Simple way: `db.links.find(url: /.com$/)`

- Or you can use `$regex` operator. `db.links.find(url:{$regex:{ /.com$/}})`.

> Why do this is because you can combine `$regex` with other operator to implement much more complex query
> `db.links.find({url: {$regex: /.com$/, $ne: "http://www.audible.com"}, title: {$ne: "Nettuts+"}},{title: 1, url: 1,_id:0})`



