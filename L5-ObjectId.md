#Lesson 5 - ObjectId

- Object Id is the primary id for each document. Usually in `_id` field.

- It's immutable and unique.

- We can customize it and let system not to create it for us.

- Beside this, `ObjectId` is created based on created-time, host, machine, and random number(Total 12 bytes), so we don't need to create a saved_on column manually.

## Get timestamp

- `ObjectId` is an object, run `getTimestamp()` you can get the iso time.

- `db.links.find()[0]._id.getTimestamp()`

```
> ISODate("2015-02-03T03:09:44Z")
```

## Customize Object Id

- You don't have to follow the **convention** in mongodb.

- Since the id like this `54d03bf85cf20f6ebb51abf5` is not so user-friendly.

(Think about http://website.com/users/54d03bf85cf20f6ebb51abf5)

- You can still cusmize your object id.

- Here's the referenced [link](http://docs.mongodb.org/manual/reference/object-id/)
