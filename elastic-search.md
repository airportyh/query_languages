# Elastic Search

Get all users (https://www.elastic.co/guide/en/elasticsearch/reference/current/query-dsl-match-all-query.html):

```
GET /_search
{
    "query": {
        "match_all": {}
    }
}
```

Get user 1 by ID:

```
GET users/_doc/1
```

Get users over 7 years of age:

```
GET _search
{
    "query": {
        "range" : {
            "age" : {
                "gt" : 7,
                "boost" : 2.0
            }
        }
    }
}
```

Select specific fields of user:

```
GET /_search
{
    "stored_fields" : ["user", "postDate"],
    "query": {
        "match_all": {}
    }
}
```

And conditional:

```
GET /_search
{
    "query": {
        "bool": {
            "must": {
                "username": "couliflower",
                "birthdate": "2008-02-08"
            }
        }
    }
}
```

Or Conditional:

```
GET /_search
{
    "query": {
        "bool": {
            "should": {
                "username": "couliflower",
                "birthdate": "2008-02-08"
            }
        }
    }
}
```

Pagination:

```
GET /_search?size=10&from=10
```

Get count with filter:

```
GET /users/_count
{
    "query": {
        "email": "couliflower@gmail.com"
    }
}
```

Expand related company: can't.

Filter by related company name: can't.