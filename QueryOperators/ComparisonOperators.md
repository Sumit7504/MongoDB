# Comparison Operators

Definition: Operators used to compare field values against specific values or criteria (such as equal, greater than, or less than).

1. $eq (Equal)
   Definition: Matches documents where the value of a field equals the specified value.

`db.students.find({ rollNumber: { $eq: 101 } });`

2. $gt (Greater Than)
   Definition: Matches documents where the value of a field is strictly greater than the specified value.

`db.products.find({ price: { $gt: 1000 } });`

3. $lt (Less Than)
   Definition: Matches documents where the value of a field is strictly less than the specified value.

`db.inventory.find({ stock: { $lt: 10 } });`

4. $gte (Greater Than or Equal To)
   Definition: Matches documents where the value is greater than or equal to the specified value.

`db.users.find({ age: { $gte: 18 } });`

5. $lte (Less Than or Equal To)
   Definition: Matches documents where the value is less than or equal to the specified value.

`db.exams.find({ score: { $lte: 40 } });`

6. $ne (Not Equal To)
   Definition: Matches documents where the value of a field does not equal the specified value.

`db.users.find({ status: { $ne: "suspended" } });`
