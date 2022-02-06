# MongoDB-CRUD-Operations
Basic commands to perform CRUD operation on Mongo DB 

- Show all Databases in mongo
```js
  show dbs
```
- Use/Create a Databases in mongo
```js
  use xyz_databse
```

- Create a Collection in a particular Databases in mongo databse
```js
  db.createCollection('users')
```

- Show all Collections in a particular Databases in mongo
```js
  show collections
```

- Search for a field in Databases in mongo
```js
 { <field1>: { <operator1>: <value1> }, ... }
 
 db.movies.find( { rated: { $in: [ "PG", "PG-13" ] } } )
```
- Update a single document in databse 
```js
  db.movies.updateOne( { title: "Tag" },
  {
    $set: {
      plot: "One month every year, five highly competitive friends
             hit the ground running for a no-holds-barred game of tag"
    }
    { $currentDate: { lastUpdated: true } }
  })
```
- Update all documents that match a specifier filter
```js
  db.listingsAndReviews.updateMany(
    { security_deposit: { $lt: 100 } },
    {
      $set: { security_deposit: 100, minimum_nights: 1 }
    }
  )
```
- The replacement document can have different fields from the original document. In the replacement document, you can omit the _id field since the _id field is immutable; however, if you do include the _id field, it must have the same value as the current value.
```js
db.accounts.replaceOne(
  { account_id: 371138 },
  { account_id: 893421, limit: 5000, products: [ "Investment", "Brokerage" ] }
)
```
### Delete All Documents
- To delete all documents from a collection, pass an empty filter document {} to the db.collection.deleteMany() method.
```
  db.movies.deleteMany({})
```
- To specify equality conditions, use : expressions in the query filter document.
- To delete all documents that match a deletion criteria, pass a filter parameter to the deleteMany() method.
```js
db.movies.deleteMany( { title: "Titanic" } )
```
- To delete at most a single document that matches a specified filter (even though multiple documents may match the specified filter) use the 
```js
  // db.collection.deleteOne() method.
  db.movies.deleteOne( { cast: "Brad Pitt" } )
  ```
