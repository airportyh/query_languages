# Firebase (v1 not the Realtime DB)

Get all users:

```
database.ref("users")
```

Get user 1 by ID:

```
database.ref("users/1")
```

Get users age older than 7

```
database.ref("users").orderByChild("age").startAt(7)
```

Select specific fields of user: *can't*.

Complex conditionals and/or: *can't*.

Pagination: *can't*.

Count users with filter: *can't*.

Expand related company name: can't.