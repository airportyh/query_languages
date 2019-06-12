# Mongo DB

Find all users

```
db.users.find()
```

Find user 507c35dd8fada716c89d0013 by ID:

```
db.users.find({ _id: ObjectId("507c35dd8fada716c89d0013")})
```

Get users over than 7:

```
db.users.find({ age: { $gt: 7 }})
```

Select specific fields of user:

```
db.users.find({}, { username: 1, email: 1 })
```

And conditional:

```
db.users.find({ username: "couliflower", birthdate: "2008-02-08" })
```

Or conditional:

```
db.users.find({ $or: [
    { username: "couliflower" },
    { birthdate: "2008-02-08" }
]})
```

Pagination:

```
db.users.find()
    .skip(10)
    .limit(10)
```

Get count of users:

```
db.users.find({ username: "couliflower@gmail.com" }).count()
```

Expand related company: *can't unless it is embedded into the user - in
which case it is automatically fetched*.

Inserts

db.users.insertOne({
    username: "flowerflower"
})

Return result of the insert is 

```
{
   "acknowledged" : true,
   "insertedId" : ObjectId("56fc40f9d735c28df206d078")
}
```

indicator of how many were inserted.
