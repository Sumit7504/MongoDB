# Projection Operators

Definition: Operators used to control which fields are included or excluded from the result set returned by a query.

1. Inclusion ($include / { field: 1 })
   Definition: Specifies which fields to include in the documents returned by a query.

`db.users.find({}, { name: 1, email: 1, \_id: 0 });`

2. Exclusion ($exclude / { field: 0 })
   Definition: Specifies which fields to omit from the returned documents.

`db.users.find({}, { passwordHash: 0 });`

3. $slice
   Definition: Controls the number of items to return from an array field within a query result.

`db.posts.find({}, { comments: { $slice: 3 } });`

4. $project (Aggregation Stage)
   Definition: Reshapes documents during an aggregation pipeline by including, excluding, renaming, or computing new fields.

`db.orders.aggregate([{ $project: { item: 1, totalPrice: { $multiply: ["$qty", "$price"] } } }]);`
