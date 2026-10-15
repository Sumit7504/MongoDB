# collection and methods

1. Counting Documents

Definition: Methods used to return the total number of documents matching a query or present in a collection.

MongoDB uses countDocuments() for accurate filtered counts and estimatedDocumentCount() for fast approximate totals.

`db.users.countDocuments({ active: true });
db.users.estimatedDocumentCount();`

2. insert() and relevant

Definition: Operations used to add one or multiple new documents into a collection.

Add new documents using insertOne() for single documents and insertMany() for multiple documents, supporting ordered/unordered inserts, write concerns, and automatic ObjectId generation.

`db.users.insertOne({ name: "Sumit", role: "Developer" });
db.users.insertMany([{ name: "Rahul" }, { name: "Aman" }]);`

3. find() and relevant

Definition: Methods used to query, retrieve, and filter documents from a collection.

Retrieves documents using find() with query filters, projections, modifiers, and related methods like findOne(), findOneAndUpdate(), findOneAndDelete(), and cursor methods (limit(), skip(), sort()).

`db.products.find({ price: { $lt: 500 } });`
`db.products.find({ price: { $lt: 500 } }).sort({ price: 1 }).limit(10);`

4. update() and relevant

Definition: Methods used to modify existing documents within a collection (e.g., updateOne, updateMany).

Modifies existing documents using updateOne(), updateMany(), and replaceOne() with update operators ($set, $unset, $inc, $push) and supports upsert operations and aggregation pipelines.

`db.users.updateOne({ name: "Sumit" }, { $set: { role: "Senior Developer" } });`

5. delete() and relevant

Definition: Methods used to remove documents from a collection based on specified filter criteria (e.g., deleteOne, deleteMany).

Removes documents using deleteOne() and deleteMany() with query filters, as well as findOneAndDelete() for atomic read-and-delete or drop() to remove entire collections.

`db.users.deleteOne({ name: "Sumit" });
db.sessions.drop();`

6. bulkWrite() and relevant

Definition: A method that executes multiple write operations (inserts, updates, deletes) in a single bulk request for high performance.
`db.users.bulkWrite([
  { insertOne: { document: { name: "Rahul" } } },
  { deleteOne: { filter: { name: "Sumit" } } }
]);
`

7. validate()

Definition: A diagnostic method that scans a collection's data and indexes for structural correctness and consistency.
`db.users.validate({ full: true });`
