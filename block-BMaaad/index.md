writeCode

Write command to

- List collections from a database.
show collections
- create a new collection in your country database which you created recently.
db.city.insertOne({title: "Patna"})

Write code to:-

- crate a database named `weather`
use weather
- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
db.createCollection("temperature", {
  capped: true,
  size: 8192,
  max: 3
})
When you attempt to insert the fourth document, MongoDB will automatically remove the oldest document(s) to accommodate the new insertion. As a result, the collection will always maintain a fixed size and store only the most recent documents.

- create a simple collection named `humidity`
- check whether `temperature` collection is capped or not ?
db.runCommand({ collStats: "temperature", scale: 1 }).capped

- Delete `humidity` collection and then the entire database(weather).
db.humidity.drop()
db.dropDatabase()