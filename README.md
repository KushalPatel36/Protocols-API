# Protocols-API

Using a Non-relational database using NoSQL which stores data about a local neighbourhood. 

The following schema outlines the structure of the database:

       $jsonSchema: {
            bsonType: "object",
            required: [ "ID", "homeownerName", "homeownerAge", "householdSize","address","postcode"],
            properties: {
                ID: {
                    bsonType: "number",
                    description: "must be unique"
                },
                homeownerName: {
                    bsonType: string",
                    description: "must be a string"
                },
                homeownerAge: {
                    bsonType: "number",
                    minimum: 0,
                    description: "must be a positive value and is required"
                },
                householdSize: {
                    bsonType: "number",
                    description: "must be a positive value and is required"
                }
                address: {
                    bsonType: "string",
                    description: "must be a string"
                }
                postcode: {
                    bsonType: "string",
                    description: "must be a string"
                }
            }
       }
       
      

GET "/neighbourhood"
Using this route, you will get back all the full database.
res.send(neighbourhood)

GET "/neighbourhood/:id"
Using this route, you will get back all information about a particular household.
res.send(neighbourhood.(req.body.id))

GET "/neighbourhood?age=(20,30)&householdSize=3"
Using this route, you will get back all households where the homeowner is aged between 20 and 30, and the household size is 3.

POST "/neighbourhood"
Using this route, you will be able to create a new household.
res.send(neighbourhood)

