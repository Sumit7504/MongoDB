# Array Operators

Definition: Operators used to query fields that contain arrays, checking for specific elements, matching array sizes, or matching sub-document structures within arrays.

1. $in (Value in Array)
   Definition: Matches documents where the value of a field equals any value in the specified array.

`db.products.find({ category: { $in: ["electronics", "clothing"] } });`

2. $nin (Value Not in Array)
   Definition: Matches documents where the value of a field does not equal any value in the specified array.

`db.users.find({ status: { $nin: ["suspended", "banned"] } });`

3. $all (Contains All Elements)
   Definition: Matches arrays that contain all the specified elements, regardless of their order or extra items in the array.

`db.posts.find({ tags: { $all: ["mongodb", "database"] } });`

4. $elemMatch (Element Match)
   Definition: Selects documents if an element in an array of nested documents satisfies multiple criteria simultaneously.

`db.students.find({ scores: { $elemMatch: { subject: "Math", marks: {$gt: 85 } } } });`

5. $size (Array Size)
   Definition: Matches arrays that contain a specified exact number of elements.

`db.articles.find({ tags: { $size: 3 } });`
