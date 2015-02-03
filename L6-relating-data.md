#Lesson 6- Relating data

- We would create a foreign key in relational database, now I'm going to introduce the way we do "join" data in nosql-way.

## Example

- Here is a quick example to demonstrate the concept of denormalizing.

(Simply ignore the query method, but I think it's very simliar to sql)

- `db.users.insert({name: 'Denny'})`

- `user = db.users.findOne({name: 'Denny'})`

- `db.links.insert({title:'Demo link', url: 'http://demo.com', userId: user._id})`

- `link = db.links.findOne({title: 'Demo link'})`

- Now we can find the user by link

(so called 'denormalize', if you don't write data too often, that would be good.)

## Principle

- There is no single principle to follow, mongoDB makes you think again and again what you need before how to do.

