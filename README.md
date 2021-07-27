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

