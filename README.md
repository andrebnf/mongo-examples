##Mongo Tutorial Command Sheet - from *newboston's* Tutorials
$ mongo

**Specify new database (it doesn't persist it straight away):**
```
use < name_of_db >
```
```
use bank
```

**List current database and all persisted databases:**
```
db
show dbs
```

**Drop current database:**
```
db.dropDatabase()
```
**Insert data from [buckyrobert's repo](https://github.com/buckyroberts/Source-Code-from-Tutorials/blob/master/Other/SampleJsonData/fake_bank_data.json)**
```
db.users.insert{
  [
    {
      "isActive": false,
      "balance": "$3,960.64",
      "age": 30,
      "eyeColor": "blue",
      "name": "Dawn Keith",or:
      "gender": "female",
      "company": "COSMOSIS",
      "email": "dawnkeith@cosmosis.com",
      "phone": "+1 (839) 437-3421",
      "address": "392 Clifford Place, Fontanelle, Arizona, 2687"
    },
    {
      "isActive": false,
      "balance": "$1,280.14",
      "age": 31,
      "eyeColor": "green",
      "name": "Bettie Eaton",
      "gender": "female",
      "company": "COMTREK",
      "email": "bettieeaton@comtrek.com",
      "phone": "+1 (861) 460-2317",
      "address": "203 Allen Avenue, Elrama, North Carolina, 4453"
    }
  ]
}
```

**List all documents (registries):**
```
db.users.find()
```

**Prettify output:**
```
db.users.find().pretty()
```

**Select by attribute:**
```
db.users.find(
  {
    "_id" : ObjectId("564a144ce1d05d069814a197")
  }
)
```
```
db.users.find(
  {
    "age": {$lt:23}
  }
)
```
**Inspect Query:**
```
db.users.find({ "age": {$lt:23} }).explain()
```
```
db.users.find({ "age": {$lt:23} }).explain("executionStats")
```

**Indexes:**
```
db.users.ensureIndex({"age": 1})
```
```
db.users.getIndexes()
```
```
db.users.dropIndex({"age": 1})
```
