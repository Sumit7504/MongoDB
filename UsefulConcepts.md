1. Read & Write Concerns
   Read and write concerns control data consistency and acknowledgment levels for database operations. Write concerns specify acknowledgment requirements from replica set members, whereas read concerns determine data consistency guarantees for queries.

- Example: Sending a registered package that requires a recipient's signature confirmation is like a high write concern, while checking a live tracking status where minor delays are acceptable resembles read concerns.

```
db.users.insertOne(
  { name: "Sumit" },
  { writeConcern: { w: "majority", wtimeout: 5000 } }
);

```

2. Cursors
   Cursors are pointers to query result sets that allow efficient iteration through large datasets without loading all documents into memory at once. They handle automatic batching, provide lazy loading, and support configurable batch sizes and timeouts.

- Example: Streaming a movie on Netflix chunks the data as you watch instead of downloading the entire gigabyte-sized file to your phone beforehand.

```
const cursor = db.users.find().batchSize(50);
while (cursor.hasNext()) {
  printjson(cursor.next());
}
```

3. Retryable Reads / Writes
   Retryable reads and writes are client-side features that automatically retry specific database operations when encountering transient network errors or temporary server unavailability. This improves application resilience and user experience in distributed cloud environments without changing application code.

- Example: A payment gateway automatically retrying a failed card transaction once if a brief network drop occurs during checkout.

```
// Retryable writes are enabled by default in modern MongoDB connection strings
const client = new MongoClient(
  "mongodb+srv://cluster.mongodb.net/?retryWrites=true&w=majority",
);
```
