# GraphQL with GraphCool

Get all users:

```
{
    allUsers {
        id
        username
        email
        birthdate
        age
    }
}
```

Get user 1 by ID:

```
{
    User (id: 1) {
        id
        username
        email
        birthdate
        age
    }
}
```

Get users over age of 7:

```
query {
    allUsers(filter: {
        age_gt: 7
    })
}
```

Get specific fields of user

```
{
    allUsers {
        username
        email
    }
}
```

And conditional

```
{
    allUsers(filter: {
        AND: [
            { username: "couliflower" },
            { birthdate: "2008-02-08" }
        ]
    }) {
        id
        username
        email
        birthdate
        age
    }
}
```

Or conditional

```
{
    allUsers(filter: {
        OR: [
            { username: "couliflower" },
            { birthdate: "2008-02-08" }
        ]
    }) {
        id
        username
        email
        birthdate
        age
    }
}
```

Pagination:


```
{
    allUsers(
        first: 10
        skip: 10
    ) {
        id
        username
        email
        birthdate
        age
    }
}
```

Get count of users:

```
query {
    _allUsersMeta(filter: {
        email: "couliflower@gmail.com"
    }) {
        count
    }
}
```

Expand related company:

query {
    allUsers {
        id
        username
        email
        company {
            id
            name
        }
    }
}

