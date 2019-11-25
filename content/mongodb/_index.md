+++
title = "MongoDB"
outputs = ["Reveal"]
+++

# MongoDB

---

> MongoDB is a general purpose, document-based, distributed database built for modern application developers and for the cloud era. No database makes you more productive.

[MongoDB Website](https://www.mongodb.com/)

---

# NoSQL

- Non relational
- Simplicity of design
- Simpler "horizontal" scaling to clusters of machines

Learn more on [Wikipedia's NoSQL entry](https://en.wikipedia.org/wiki/NoSQL)

---

## How MongoDB Works

- Stores data in flexible, JSON-like documents
- Maps to the objects in your application code
- Ad hoc queries, indexing, and real time aggregation
- Distributed database at its core
- Free to use (40,000,000+ downloads)

Learn more about [MongoDB architecture](https://www.mongodb.com/mongodb-architecture)

---

### With Express

```js
var MongoClient = require("mongodb").MongoClient;
var dbUrl = "mongodb://localhost:27017/animals";

MongoClient.connect(dbUrl, (err, client) => {
  if (err) throw err;
  var db = client.db("animals");
  db.collection("mammals")
    .find()
    .toArray(function(err, result) {
      if (err) throw err;
      console.log(result);
    });
});
```

---

## Inserting Data

Add a query that adds three documents to the documents collection

```js
const insertDocuments = function(db, callback) {
  // Get the documents collection
  const collection = db.collection("documents");
  // Insert some documents
  collection.insertMany([{ a: 1 }, { a: 2 }, { a: 3 }], (err, result) => {
    assert.equal(err, null);
    assert.equal(3, result.result.n);
    assert.equal(3, result.ops.length);
    console.log("Inserted 3 documents into the collection");
    callback(result);
  });
};
```

---

## Find All Documents

Add a query that returns all the documents

```js
const findDocuments = function(db, callback) {
  // Get the documents collection
  const collection = db.collection("documents");
  // Find some documents
  collection.find({}).toArray(function(err, docs) {
    assert.equal(err, null);
    console.log("Found the following records");
    console.log(docs);
    callback(docs);
  });
};
```

---

#### Find Documents with a Query Filter

Add a query filter to find only documents which meet the query criteria

```js
const findDocuments = function(db, callback) {
  // Get the documents collection
  const collection = db.collection("documents");
  // Find some documents
  collection.find({ a: 3 }).toArray(function(err, docs) {
    assert.equal(err, null);
    console.log("Found the following records");
    console.log(docs);
    callback(docs);
  });
};
```

Only the `'a':3` document should be returned.

---

### Update a document

The following operation updates a document in the documents collection

```js
const updateDocument = function(db, callback) {
  // Get the documents collection
  const collection = db.collection("documents");
  // Update document where a is 2, set b equal to 1
  collection.updateOne({ a: 2 }, { $set: { b: 1 } }, function(err, result) {
    assert.equal(err, null);
    assert.equal(1, result.result.n);
    console.log("Updated the document with the field a equal to 2");
    callback(result);
  });
};
```

---

### Remove a Document

Remove the document where the field a is equal to 3.

```js
const removeDocument = function(db, callback) {
  // Get the documents collection
  const collection = db.collection("documents");
  // Delete document where a is 3
  collection.deleteOne({ a: 3 }, function(err, result) {
    assert.equal(err, null);
    assert.equal(1, result.result.n);
    console.log("Removed the document with the field a equal to 3");
    callback(result);
  });
};
```

---

Thanks to MongoDB's [quick start guide](https://mongodb.github.io/node-mongodb-native/3.1/quick-start/quick-start/) for the code samples.
