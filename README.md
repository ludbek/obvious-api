> This is a work in progress. Feel free to open an issue or a PR.

# Obvious API
`Obvious API` is an obvious `REST API standard`.

## Motivation
While there is a single [REST API standard](#rest-api), there are multiple implementations in the wild.  
They are different from company to company and team to team.  
The biggest variations can be seen in the design of the URLs and use of the HTTP methods.  
Sadly they are complex, easily misunderstood and don't have any names.
It is difficult to communicate and get consensus in a team.  
`Obvious API` is an attempt to solve these problems.

## Standard
### Query
```
GET [/namespace]/<resource>/<action>[?query-params]
```
If there are any unknown query parameters or the known query parameters are not sorted in ascending order, the API should return 400.

### Mutation
```
POST [/namespace]/<resource>/<action> + [body]
```
  
### Namespace
It is an optional path that helps to segregate the services.  
It is usually a service name and should be a noun.  
e.g. `/auth`

### Resource
It could be the name of a datastore like table or a pseudo resource to hold bunch of actions together.  
It should be a singular noun.  
e.g. `/auth/user`. 

### Action
It is the name of a task that belongs to a resource.  
It should be a verb.  
e.g. `/auth/user/activate`, `/auth/user/deactivate`. 

#### Fundamental actions for a resource
They are named after the CRUD operations.

##### create
```
POST /user/create + body
```

##### read
```
GET /user/read?page=1&offset=0
GET /user/read-one?id=1
```

##### update
```
POST /user/update + body
```

##### delete
```
POST /user/delete + body
```

## Obvious API is a REST API

|Rest API features.       | Support.           |
|-------------------------|--------------------|
| Client-Server Separation| :white_check_mark: |
| Uniform Interface       | :white_check_mark: |
| Stateless               | :white_check_mark: |
| Layered System          | :white_check_mark: |
| Cacheable               | :white_check_mark: |

## Rest API
Check out [Architectural Styles and the Design of Network-based Software Architectures](https://www.ics.uci.edu/~fielding/pubs/dissertation/fielding_dissertation_2up.pdf) Chapter 5 to know about REST API standard.
