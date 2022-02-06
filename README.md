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
