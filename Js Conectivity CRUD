const { MongoClient } = require('mongodb');

const uri = 'mongodb://localhost:27017';
const client = new MongoClient(uri, { useNewUrlParser: true, useUnifiedTopology: true });


function DisplayData(result)
{
    result.forEach (element => {
        console.log(element)
    });
}

async function connect()
{
    await client.connect();
    console.log('Connected to the database');
}


async function insertData(data)
{
    connect();
    let Db = client.db("Company");
    let MyCollection = Db.collection("Employee");

    MyCollection.insertOne(data);
    console.log("Data inserted successfully")

  
}


async function UpdateData(filter, update) 
{
    const db = client.db("Company");
    const myCollection = db.collection("Employee");
    await myCollection.updateOne(filter, update);
    console.log('Document updated successfully');
}

async function DeleteData(obj)
{
    const db = client.db("Company");
    const myCollection = db.collection("Employee");
    await myCollection.deleteOne(obj);
    console.log('Document deleted successfully');


}


async function readData()
{
    connect();
    let Db = client.db("Company");
    let MyCollection = Db.collection("Employee");
    let result = await MyCollection.find().toArray();
    // console.log(result)
    DisplayData(result);
    

}


// insertData({"Name":"Satyam Doe","Age": 18});
// UpdateData({ Name: 'Satyam Doe' }, { $set: { Age: 26 } }); // Update existing document
// DeleteData({ Name: 'Satyam Doe' });
// readData();
