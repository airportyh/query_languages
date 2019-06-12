# Salesforce SOQL

Get all users:

```
SELECT
    id,
    username,
    email,
    birthdate,
    age
FROM
    users
```

Get user 1 by ID:

```
SELECT
    Id,
    Username,
    Email,
    BirthDate,
    Age
FROM
    User
WHERE
    Id = 1
```

Get users of age 7 years or older:

```
SELECT
    Id,
    Username,
    Email,
    BirthDate,
    Age
FROM
    User
WHERE
    Age > 7
```

Select specific fields of user:

```
SELECT
    Username,
    Email
FROM
    User
```

And conditional

```
SELECT
    Username,
    Email
FROM
    User
WHERE
    Username = "couliflower" AND
    Birthdate = "2008-02-08"
```

Or conditional

```
SELECT
    Username,
    Email
FROM
    User
WHERE
    Username = "couliflower" OR
    Birthdate = "2008-02-08"
```

Pagination:

```
SELECT
    Username,
    Email
FROM
    User
LIMIT
    10
OFFSET
    10
```

Get count of users with filter:

```
SELECT
    Count(Id)
FROM
    User
WHERE
    Email = 'couliflower@gmail.com'
```

Expand related company:

*Note: this deviates from normal SQL*.

```
SELECT
    User.Id,
    User.Name,
    (
        SELECT
            Company.Id, 
            Company.Name
        FROM
            Company
    )
FROM
    User  
```

Filter by related company name:

```
SELECT
    Id,
    Name,
    Email
FROM
    User
WHERE
    Company.Name = 'Microsoft'
```