# GraphQL @connection
## Add relationships between types
- we use the following directive in order to make a relation between my tables=> @connection
- ther is just three types of connection in the GraphQL:
   - one to one
   - one to many
   - many to one
- if you want to implement many to many=> you can do that by implementing two `one to many` and `many to one` relation     
```
directive @connection(keyName: String, fields: [String!]) on FIELD_DEFINITION
```
- fields=> can filled to indicate which field will be quired by to connect to object
- keyName=> if you want to specify secondary index
- if you don't add keyName the @connection will query the target table's primary index
## Has one
- it's the one to one relation 
- you will write the two tables with add first type and after that @model
- add the fields in every one
- add additional field in the mapping type, and assert to it @connection
- you can add the field in @connection...
- after that you can make your project class, and all fields to it, and the field with mapping feature add it like you make any object
```
type Project @model {
  id: ID!
  name: String
  teamID: ID!
  team: Team @connection(fields: ["teamID"])
}

type Team @model {
  id: ID!
  name: String!
}
```

## Has many
- it's the one to many relation
- the differ from on to one by addy a KeyName for the connection to specify by what i will query the table, and with adding field to connect from, and on another type we have to add @key and specify the name of the key==> the same of KeyName, and we have to add the fields on the same model

## Belongs to
- connection bi-directional is that we talk about in here
- just add many to one connection to table already have one to many relation
## Many-to-many connections
- here you have to use two one to many relation, with @connection, @key, and a joingin @model
## Alternative definition
- the old way to do the connection will be like this:   
```
directive @connection(name: String, keyField: String, sortField: String, limit: Int) on FIELD_DEFINITION
```
- i recomend to use the new way
## Limit
- the number of nested objects is 100 you can add a limit by `@connection(limit="anyNumber")`

