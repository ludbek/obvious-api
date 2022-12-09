# Sane API
Sane API is an obvious REST API standard.

## Motivation

## Query
### Non Cachable
```
GET [/namespace]/<resource>/<action>[?query-params]
```

### Cachable
```
GET [/namespace]/<resource>/<action>/<Base64 URI Encoded sorted query params>
```
The base64 URI encoded value must be validated to make sure it was created
using the sorted query params. Also we need to throw error if unknown query params
are passed.

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
e.g. `/auth/user`

## Action
It is the name of a task that belongs to a resource.
It should be a verb.
e.g. `/auth/user/activate`, `/auth/user/deactivate`

### Fundamental actions
They are named after the CRUD operations.

#### create
```
POST /user/create
```

#### read
```
GET /user/read
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
1. Client-Server Separation
2. Uniform Interface
- requests and responses must follow a common protocol
3. Stateless
4. Layered System
5. Cacheable
Client side cache
