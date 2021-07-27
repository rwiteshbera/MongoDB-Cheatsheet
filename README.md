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

### Insert data into MongoDB collection
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

### Insert array of documents into MongoDB collection
```
> db.COLLECTION_NAME.insertMany([Store documents as array objects])
```
#### *Example*
Here `geeks` is a collection in which I have stored documents.
```
> db.geeks.insertMany([
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

### Find/ Query document from MongoDB collection
```
> db.COLLECTION_NAME.find()
```
#### *Example*
```
> db.geeks.find()
{ "_id" : ObjectId("6100483bb398f4a34021554b"), "First_Name" : "Rwitesh", "Last_Name" : "Bera", "Phone" : "9876543210", "id" : 1 }
{ "_id" : ObjectId("6100483bb398f4a34021554c"), "First_Name" : "Jishan", "Last_Name" : "Bhattacharya", "Phone" : "9080706050", "id" : 2 }
{ "_id" : ObjectId("6100483bb398f4a34021554d"), "First_Name" : "Archisman", "Last_Name" : "Saha", "Phone" : "9192939495", "id" : 3 }
```

### Display the results in formatted way
```
> db.COLLECTION_NAME.find().pretty()
```

### Search in Database
#### *Example*
```
> db.geeks.find({"id" : 1})
{ "_id" : ObjectId("6100483bb398f4a34021554b"), "First_Name" : "Rwitesh", "Last_Name" : "Bera", "Phone" : "9876543210", "id" : 1 }
```

### Count the number of documents
#### *Example*
```
> db.geeks.count()
3
```

### Delete a document
```
> db.COLLECTION_NAME.remove(DELLETION_CRITTERIA)
```
It will delete the document which has the given criteria.
#### *Example*
```
> db.geeks.remove({"First_Name" : "Rwitesh"})
WriteResult({ "nRemoved" : 1 })
```
If you don't specify any criteria, then MongoDB will delete the entire documents from the collection.
```
> db.geeks.remove({})
```

### Limit() Methods
Limit method accepts one number argument, which is the number of documents you want to be displayed.
```

> db.COLLECTION_NAME.find().limit(NUMBER)
```

### Skip() Method
Skip method accepts one number argument and is used to skip the number of documents.
```
> db.COLLECTION_NAME.find().limit(NUMBER).skip(NUMBER)
```

### Sort() Method
Sort method is used to display documents in sorting order. Make sure that your each document has one key value.

##### Ascending Order
```
> db.COLLECTION_NAME.find().sort({KEY:1})
```

##### Descending Order
```
> db.COLLECTION_NAME.find().sort({KEY:-1})
```

### Update a field in document
```
> db.COLLECTION_NAME.update(SELECTION_CRITERIA, UPDATED_DATA)
```
#### *Example*
Updating the id here
```
> db.geeks.update({"First_Name" : "Rwitesh"}, 
... { 
... "First_Name" : "Rwitesh",
... "Last_Name" : "Bera",
... "Phone" : "9876543210",
... "id" : 999 
... })
```