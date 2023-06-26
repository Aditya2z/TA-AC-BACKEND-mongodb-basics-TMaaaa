writeCode

Write code to:-

- create a database named `sports`.
use sports
- list all databases present in local mongod server.
show dbs
- create 3 collections named `cricket`, `football`, `TT` in sports databse.
db.createCollection("cricket")
db.createCollection("football")
db.createCollection("TT")

- add multiple players in those collections which should have fields like `name`, `age` and `email` and `bid_price`.
db.cricket.insertMany([
  { name: "Player 1", age: 25, email: "player1@example.com", bid_price: 1000 },
  { name: "Player 2", age: 28, email: "player2@example.com", bid_price: 1500 },
  { name: "Player 3", age: 30, email: "player3@example.com", bid_price: 1200 }
])

db.football.insertMany([{ name: "Player A", age: 27, email: "playerA@example.com", bid_price: 2000 },
{ name: "Player B", age: 29, email: "playerB@example.com", bid_price: 1800 },
{ name: "Player C", age: 24, email: "playerC@example.com", bid_price: 1600 }])


db.TT.insertMany([{ name: "Player X", age: 26, email: "playerX@example.com", bid_price: 2200 },
{ name: "Player Y", age: 31, email: "playerY@example.com", bid_price: 1900 },
{ name: "Player Z", age: 23, email: "playerZ@example.com", bid_price: 1400 }])



- list all collections in sports database.
show collections

- rename `TT` collection to `tennis`.
db.TT.renameCollection("tennis")

- create a capped collection called `khokho` which should have max 3 documents.
db.createCollection("khokho", { capped: true, size: 8192, max: 3 })


  Try inserting more than 3 and see what happens?
  If the collection has reached its maximum document limit (in this case, 3 documents) and you attempt to insert another document, the new document will overwrite the oldest document in the collection. 

- check whether a collection is capped or not?
db.runCommand({collStats: "khokho", scale: 1}).capped

- drop all documents from `football` collection.
db.football.deleteMany({})

- delete cricket collection completely.
db.cricket.drop()

- delete sports database.
db.dropDatabase()

- check which database you are connected to ?
sports

- connect to test database
use test