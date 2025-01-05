# MongoDB $inc Operator Error
This repository demonstrates a common error when using the `$inc` operator in MongoDB update queries. The `$inc` operator is used to increment a numerical field by a specified value. However, if the specified value is not a number, the update operation will fail silently, without throwing an error.

## Bug
The bug is in the usage of the `$inc` operator. In the original code snippet, the value to increment is a string '1', causing an error.

## Solution
The solution is to ensure that the increment value is a number:

```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```