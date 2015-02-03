# Lesson 9 - Much More Operators 

## Simple logistics operators

- `$ne` : not equal.

- `$or` : I've mentioned it in  the previous lesson, now check how it works.

`db.users.find({$or: [{"name.first": "John"}, {"name.first": "Bob"}]})`

- Each condition is placed in an object, of course you can set more than two conditions:

`db.users.find({$or: [{"name.first": "John"}, {"name.first": "Bob"}, {age: {$ne: 31}}]})`


- `$and` : just and.

- `$nor`: match none of the elements in the condition array.

- `$exists`: Select the documents have this field. This is very different from sql-liked database.If we use sql-liked databased , you mind query something like `NOT NULL` for specific column, but since we don't have a schema for nosql-liked database, we might even not have this field, that's why we need `$exists` operator.


`db.users.find({name: {$exists: true}})`

- `$mod` : `$mod: [5, 0]` will select the value %5 === 0

- `$not` : `$not: {$mod:[5,0]}` will select the value %5 !== 0

- `$where` : Example => `db.users.find({$where: 'this.name.first === "Bob"'})`

（`db.users.find({$where: 'this.name.first === "Bob"'})`）



