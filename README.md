# MongoDB CRUD Operations

## Create a Database and Collection

1. Create a database called "contact": `use contact`

2. Create a collection called "contactlist": `db.createCollection("contactlist")`

## Insert Data

3. Insert these documents in "contactlist": 
`db.contactlist.insertMany([
{ "Last name": "Ben Lahmer", "First name": "Fares", "Email": "fares@gmail.com", "age": 26 },
{ "Last name": "Kefi", "First name": "Seif", "Email": "kefi@gmail.com", "age": 15 },
{ "Last name": "Fatnassi", "First name": "Sarra", "Email": "sarra.f@gmail.com", "age": 40 },
{ "Last name": "Ben Yahia", "First name": "Rym", "age": 4 },
{ "Last name": "Cherif", "First name": "Sami", "age": 3 }
])`


## Retrieve Data

4. Display all of the contacts list: `db.contactlist.find()`


5. Display all the information about only one person using his ID. Replace <ObjectId> with the ID of the document you want to retrieve:
`db.contactlist.findOne({_id: ObjectId("<ObjectId>")})`

6. Display all the contacts with an age >18: `db.contactlist.find({age: {$gt: 18}})`

7. Display all the contacts with an age>18 and name containing "ah": `db.contactlist.find({$and: [{age: {$gt: 18}}, {"Last name": /ah/i}]})` //i for insentive case


## Update Data

8. Change the contact's first name from "Kefi Seif" to "Kefi Anis". Replace <ObjectId> with the ID of the document you want to update:
`db.contactlist.updateOne({_id: ObjectId("<ObjectId>")}, {$set: {"First name": "Kefi Anis"}})`

## Delete Data

9. Delete the contacts that are aged under <5: `db.contactlist.deleteMany({age: {$lt: 5}})`

## Retrieve Data

10. Display all of the contacts list: `db.contactlist.find()`






