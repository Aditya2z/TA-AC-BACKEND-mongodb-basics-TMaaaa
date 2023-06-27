writeCode

Write code to:-

- create a database named `mountains`
use mountains
- a collection inside that database named `himalayas`
db.createCollection("himalayas")
- insert 1 document into that collection `{name: 'Dhauldhar range', height: '4000 mtrs'}`
db.himalayas.insertOne({name: 'Dhauldhar range', height: '4000 mtrs'})

- insert multiple document using insertMany command
 const mountainRanges = [{ name: "Pir Panjal Range", height: "4000 mtrs" }, { name: "Zanskar Range", height: "4000 mtrs" }, { name: "Karakoram Range", height: "4000 mtrs" }, { name: "Alborz Range", height: "4000 mtrs" }, { name: "Taurus Mountains", height: "4000 mtrs" }];
 db.himalayas.insertMany(mountainRanges);
 
- find all documents from mountains
show collections
db.himalayas.find()

- find a single document using name
db.himalayas.findOne({name : "Taurus Mountains"})