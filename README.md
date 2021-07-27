# MongoDB Cheatsheet
### View all database
```
> show dbs
```

### Create new database
```
> use [Database name]
```

### View current database
```
> db
```

### Delete database
```
> db.dropDatabase()
```

### Switch to a database
```
> use [Database name]
```

### Show collections
```
> show collections
```
### Create a collection named `myCollection`
```
> db.createCollection('myCollection')
```
### Drop or delete a collection named `myCollection`
```
> db.myCollection.drop()
```
### Insert data into MongoDB Collection
```
> db.COLLECTION_NAME.insert(document)
```
#### *Example*
```
> db.myCollection.insert({
... ... 'name': 'Rwitesh',
... ... 'lang': 'Java',
... ... 'id': 1
... ... })
WriteResult({ "nInserted" : 1 })
```
Here `myCollection` is the name of the collection.

> [NOTE]
> You can use `db.myCollection.insertOne(document)`, if you want to add only one document.

### Insert array of documents into MongoDB Collection
Here `geeks` is a collection in which I have stored documents.
```
db.geeks.insertMany([
... {
... First_Name : "Rwitesh",
... Last_Name : "Bera",
... Phone : "9876543210",
... id : 1
... },
... {
... First_Name : "Jishan",
... Last_Name : "Bhattacharya",
... Phone : "9080706050",
... id : 2
... },
... {
... First_Name : "Archisman",
... Last_Name : "Saha",
... Phone : "9192939495",
... id : 3
... }
... ])
```
