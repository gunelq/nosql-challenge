# nosql-challenge
Eat Safe, Love, 
Part 1:
-For this task we imported the data provided in the establishments.json in MongoDb.Created the database uk_food and the collection establishments.
-Created an instance of the Mongo Client.
- Confirmed that we created the database and loaded the data properly:
- Listed the databases we have in MongoDB. Confirmed that uk_food is listed.
- Listed the collection(s) in the database to ensure that establishments is there.
- Found and displaed one document in the establishments collection using find_one and displed with pprint.
- Assigned the establishments collection to a variable to prepare the collection for use.

Part 2: Updated the Database

 Added the following information to the database:
{
    "BusinessName":"Penang Flavours",
    "BusinessType":"Restaurant/Cafe/Canteen",
    "BusinessTypeID":"",
    "AddressLine1":"Penang Flavours",
    "AddressLine2":"146A Plumstead Rd",
    "AddressLine3":"London",
    "AddressLine4":"",
    "PostCode":"SE18 7DY",
    "Phone":"",
    "LocalAuthorityCode":"511",
    "LocalAuthorityName":"Greenwich",
    "LocalAuthorityWebSite":"http://www.royalgreenwich.gov.uk",
    "LocalAuthorityEmailAddress":"health@royalgreenwich.gov.uk",
    "scores":{
        "Hygiene":"",
        "Structural":"",
        "ConfidenceInManagement":""
    },
    "SchemeType":"FHRS",
    "geocode":{
        "longitude":"0.08384000",
        "latitude":"51.49014200"
    },
    "RightToReply":"",
    "Distance":4623.9723280747176,
    "NewRatingPending":True
}
Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned only the BusinessTypeID and BusinessType fields.
Updated the new restaurant with the BusinessTypeID you found.

Checked how many documents contain the Dover Local Authority. Then, removed establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they were deleted.
Some of the number values are stored as strings, when they should be stored as numbers.

Used update_many to convert latitude and longitude to decimal numbers.
Used update_many to convert RatingValue to integer numbers.


Part 3: Exploratory Analysis

- RatingValue refers to the overall rating decided by the Food Authority and ranges from 1-5. The higher the value, the better the rating.
Note: This field also includes non-numeric values such as 'Pass', where 'Pass' means that the establishment passed their inspection but isn't given a number rating. We will coerce non-numeric values to nulls during the database setup before converting ratings to integers.
The scores for Hygiene, Structural, and ConfidenceInManagement work in reverse. This means, the higher the value, the worse the establishment is in these areas.
Used count_documents to display the number of documents contained in the result.
Displed the first document in the results using pprint.
Converted the result to a Pandas DataFrame, print the number of rows in the DataFrame, and displed the first 10 rows.

Anwered to the questions:
Which establishments have a hygiene score equal to 20?
Which establishments in London have a RatingValue greater than or equal to 4?
What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"?
How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas.


