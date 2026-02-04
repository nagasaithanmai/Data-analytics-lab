# Exercise 2: NoSQL Big Data Management

## Step 1: Create and Use Database
```js
use DataAnalyticsDB
db.students.insertMany([
  { rollno: 101, name: "Arun", dept: "CSE", marks: 85 },
  { rollno: 102, name: "Divya", dept: "CSE", marks: 92 },
  { rollno: 103, name: "Karthik", dept: "ECE", marks: 78 }
])
db.students.find()
db.students.find({ dept: "CSE" })
db.students.updateOne(
  { rollno: 101 },
  { $set: { marks: 88 } }
)
db.students.deleteOne({ rollno: 103 })
db.students.aggregate([
  { $group: { _id: "$dept", avgMarks: { $avg: "$marks" } } }
])
