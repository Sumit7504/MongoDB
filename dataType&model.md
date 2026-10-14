# Data Types and Data Model

# 1. BSON vs JSON

JSON is a lightweight text-based format used for data interchange, while BSON (Binary JSON) is MongoDB's binary-encoded format that supports more data types and faster machine parsing.

`// JSON format (Text-based)
{
  "name": "Sumit",
  "status": "Active"
}`

# 2. Embedded Objects & Arrays

The ability to nest sub-documents (objects) and lists (arrays) directly within a main document, keeping related data together.

`{
  name: "Sumit",
  address: { city: "Gwalior", pincode: 474001 }, // Embedded Object
  hobbies: ["Coding", "Trading"]                 // Array
}`

# Breakdown of all MongoDB BSON data types:

1. Double - Stores 64-bit floating-point numbers.
   `{ rating: 4.5 }`

2. String - Stores text values using UTF-8 encoding.
   `{ name: "Sumit" }`

3. Object - Embedded documents or nested key-value pairs inside a document.
   `{ address: { city: "Gwalior", zip: 474001 } }`

4. Array - A list containing a collection of values or documents.
   `{ hobbies: ["coding", "trading"] }`

5. Binary Data - Stores byte arrays of raw binary data.
   `{ signature: BinData(0, "SGVsbG8=") } `

6. Undefined - Represents an unassigned or undefined value (deprecated in modern BSON).
   `{ legacyField: undefined } `

7. Object ID - A unique 12-byte identifier used for document \_id fields.
   `{ \_id: ObjectId("65f1a2b3c4d5e6f7a8b9c0d1") } `

8. Boolean - Stores logical true or false values.
   `{ isActive: true }`

9. Date - Stores the current date and time as milliseconds since the Unix epoch.
   `{ createdAt: new Date() } `

10. Null - Represents a null or explicitly empty value.
    `{ middleName: null } `

11. Regular Expression - Stores regular expression patterns for text matching.
    `{ pattern: /^sumit/i } `

12. JavaScript - Stores JavaScript code snippets directly in the database.
    `{ script: function() { return this.age \* 2; } }`

13. Symbol - Identical to a string, historically used for programming language symbols (mostly deprecated).
    `{ sym: Symbol("identifier") } `

14. Int32 / Int - Stores standard 32-bit signed integer numbers.
    `{ age: NumberInt(23) } `

15. Int64 / Long - Stores 64-bit signed integer numbers for very large counts.
    `{ views: NumberLong("9876543210") } `

16. Timestamp - A special 64-bit internal BSON timestamp used for replication and sharding operations.
    `{ ts: Timestamp(1699999999, 1) }`

17. Decimal128 - High-precision 128-bit floating-point numbers designed for financial accuracy.
    `{ balance: Decimal128("10500.75") }`

18. Min Key - Compares lower than every other BSON data type, used for edge-case indexing.
    `{ lowerLimit: MinKey() }`

19. Max Key - Compares higher than every other BSON data type, used for edge-case indexing.
    `{ upperLimit: MaxKey() }`
