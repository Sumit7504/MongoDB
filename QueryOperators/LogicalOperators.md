# Logical Operators

Definition: Operators used to combine multiple query conditions using boolean logic (AND, OR, NOT, NOR).

1. $and (Logical AND)
   Definition: Joins query clauses with a logical AND, matching documents that satisfy all the specified conditions.

`db.users.find({$and: [{ status: "active" }, { age: { $gt: 21 } }] });`

2. $or (Logical OR)
   Definition: Joins query clauses with a logical OR, matching documents that satisfy at least one of the conditions.

`db.users.find({$or: [{ role: "admin" }, { role: "moderator" }]});`

3. $not (Logical NOT)
   Definition: Inverts the effect of a query condition, matching documents where the specified condition is false.

`db.products.find({price: { $not: { $gt: 500 } }});`

4. $nor (Logical NOR)
   Definition: Joins query clauses with a logical NOR, matching documents that fail to meet all of the listed conditions.

`db.users.find({$nor: [{ status: "suspended" }, { status: "pending" }]});`
