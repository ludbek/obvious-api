# Obvious API
Obvious API is an obvious REST API standard.

## Motivation

## Query
### Non Cachable
```
GET [/namespace]/<resource>/<action>[?query-params]
```
If there are any unknown params or the query params are not sorted, the API should return 400.

## Mutation
```
POST [/namespace]/<resource>/<action>[<body>]
```
  
## Namespace
It is an optional path that helps to segregate the resources.  
It usually is a service name and should be a noun.  
e.g. `/auth`

## Resource
It could be the name of a datastore like table or a pseudo resource to hold bunch of actions together.  
It should be a noun.  
e.g. `/auth/user`. 

## Action
It is the name of a task that belongs to a resource.  
It should be a verb.  
e.g. `/auth/user/activate`, `/auth/user/deactivate`. 

### Fundamental actions
They are named after the CRUD operations.

#### create
```
POST /user/create
```

#### query (read)
```
GET /user/query?page=1&offset=0
GET /user/query-one?id=1
```

#### update
```
POST /user/update
```

#### delete
```
POST /user/delete
```

## Sane API is a REST API

|Rest API features.       | Support.           |
|-------------------------|--------------------|
| Client-Server Separation| :white_check_mark: |
| Uniform Interface       | :white_check_mark: |
| Stateless               | :white_check_mark: |
| Layered System          | :white_check_mark: |
| Cacheable               | :white_check_mark: |
