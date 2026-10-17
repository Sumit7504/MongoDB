# Element Operators

Definition: Operators used to query documents based on whether fields exist, match a specific data type, or match regular expression patterns.

1. $exists (Field Existence)
   Definition: Matches documents based on the presence or absence of a specific field.

`db.users.find({ phoneNumber: { $exists: true } });`

2. $type (Data Type Matching)
   Definition: Matches documents where the field value is an instance of a specified BSON data type (e.g., number, string, array).

`db.inventory.find({ price: { $type: "decimal" } });`

3. $regex (Regular Expression Pattern Matching)
   Definition: Provides regular expression capabilities for pattern matching strings in field values.

`db.products.find({ name: { $regex: /^Smart/i } });`
