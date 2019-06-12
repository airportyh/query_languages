# JSON Server

Get all Users:

```
GET /users
```

Get user 1 by ID:

```
GET /users/1
```

Get users over than 7:

```
GET /users?age_gt=7
```

Get specific fields of user: *can't*.

And Conditional

```
GET /users?username=couliflower&birthdate=2008-02-08
```

Or Conditional: can't.

Pagination:

```
GET /users?_start=10&_limit=10
```

Get count of users: *can't*.

Expand relationships

```
GET /users?_expand=company
```

Filter by related company name:

```
GET /users?company.name=Microsoft
```