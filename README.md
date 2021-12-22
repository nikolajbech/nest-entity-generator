# Nest entity genrator

...a tool for generating entities, dtos and resolvers fast!

The input for the generation is a JSON file called <entityName>.entity.json:

```
{
  "entityName": "Like", // name of the entity
  "tableName": "likes", // name of the database table
  "subscribable": true, // creates a subscription for when an object is added
  "softDelete": false, // is soft delete by default
  "columns": [
    {
      "type": "int" | "float" | "string" | "boolean",
      "name": "fullName", // names should always start with a lower case letter
      "nullable": true,
      "creatable": false, // makes it impossible to create to begin with
      "defaultValue": 0, // the value it will default to (should be of same type)
      "updatable": true // make it possible to update
    },
    {
      "type": "manyToOne",
      "nullable": true,
      "relatesTo": "User" // to rations should always start with an upper case letter
    },
    {
      "type": "oneToMany",
      "relatesTo": "Comment"
    }
  ]
}
```