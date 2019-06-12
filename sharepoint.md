# Sharepoint API

Get all users:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items
```

Get user 1 by ID:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items(1)
```

Get users with age greather than 7:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$filter=Age gt 7
```

Select specific fields of user:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$select=Username,Email
```

And conditional:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$filter=(Username eq 'couliflower') and (BirthDate eq '2008-02-08')
```

Or conditional:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$filter=(Username eq 'couliflower') or (BirthDate eq '2008-02-08')
```

Pagination:

Skip doesn't work: https://sharepoint.stackexchange.com/questions/126565/issue-with-skip-in-rest-api

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$top=10
```

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$top=10&$skiptoken=Paged=TRUE%26p_ID=12
```

Count users by filter: *can't*.

Expand related companies:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$expand=Company&$select=ID,Title,Company/ID,Company/Title
```

Filter by related company name:

```
GET <app_root>/_api/web/lists/GetByTitle('Users')/Items?$filter=Company/Name=Microsoft
```