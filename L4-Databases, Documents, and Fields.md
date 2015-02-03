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

- Recap: `use DATABASE_NAME` can create a database.

## Create collection

- `db.links` would create collection named `links` for you.

- `db.links.count()` can see how many document in links now.