**MongoDB Commands Cheat Sheet**

### **1. Database Commands**
- **Show all databases:**  
  ```bash
  show dbs
  ```
- **Switch to a database (or create a new one):**  
  ```bash
  use myDatabase
  ```
- **Show the current database:**  
  ```bash
  db
  ```
- **Drop a database:**  
  ```bash
  db.dropDatabase()
  ```

### **2. Collection Commands**
- **Show all collections in the database:**  
  ```bash
  show collections
  ```
- **Create a collection:**  
  ```bash
  db.createCollection("myCollection")
  ```
- **Drop a collection:**  
  ```bash
  db.myCollection.drop()
  ```

### **3. Insert Documents**
- **Insert one document:**  
  ```bash
  db.myCollection.insertOne({ name: "Ashutosh", age: 25 })
  ```
- **Insert multiple documents:**  
  ```bash
  db.myCollection.insertMany([
    { name: "Dytto", age: 24 },
    { name: "Chris Brown", age: 26 }
  ])
  ```

### **4. Find Documents**
- **Find all documents:**  
  ```bash
  db.myCollection.find()
  ```
- **Find one document:**  
  ```bash
  db.myCollection.findOne({ name: "Rahul" })
  ```
- **Find with condition:**  
  ```bash
  db.myCollection.find({ age: { $gt: 24 } })
  ```
- **Pretty print results:**  
  ```bash
  db.myCollection.find().pretty()
  ```

### **5. Update Documents**
- **Update one document:**  
  ```bash
  db.myCollection.updateOne(
    { name: "Rahul" },
    { $set: { age: 26 } }
  )
  ```
- **Update multiple documents:**  
  ```bash
  db.myCollection.updateMany(
    { age: { $lt: 25 } },
    { $set: { status: "young" } }
  )
  ```

### **6. Delete Documents**
- **Delete one document:**  
  ```bash
  db.myCollection.deleteOne({ name: "Rahul" })
  ```
- **Delete multiple documents:**  
  ```bash
  db.myCollection.deleteMany({ age: { $lt: 25 } })
  ```

### **7. Indexing**
- **Create an index:**  
  ```bash
  db.myCollection.createIndex({ name: 1 })
  ```
- **Show indexes:**  
  ```bash
  db.myCollection.getIndexes()
  ```

### **8. Aggregation**
- **Simple aggregation example:**  
  ```bash
  db.myCollection.aggregate([
    { $group: { _id: "$age", count: { $sum: 1 } } }
  ])
  ```

### **9. User Management**
- **Create a new user:**  
  ```bash
  db.createUser({
    user: "admin",
    pwd: "password123",
    roles: [{ role: "readWrite", db: "myDatabase" }]
  })
  ```
- **Show users:**  
  ```bash
  show users
  ```


