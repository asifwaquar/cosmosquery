# cosmos query

eg. 

##### Anderson family data


    {
      "id": "AndersenFamily",
      "lastName": "Andersen",
      "parents": [
         { "firstName": "Thomas" },
         { "firstName": "Mary Kay"}
      ],
      "children": [
         {
             "firstName": "Henriette Thaulow",
             "gender": "female",
             "grade": 5,
             "pets": [{ "givenName": "Fluffy" }]
         }
      ],
      "address": { "state": "WA", "county": "King", "city": "Seattle" },
      "creationDate": 1431620472,
      "isRegistered": true
    }
    
    
   ##### Wakefield Family data
   
     {
      "id": "WakefieldFamily",
      "parents": [
          { "familyName": "Wakefield", "givenName": "Robin" },
          { "familyName": "Miller", "givenName": "Ben" }
      ],
      "children": [
          {
            "familyName": "Merriam",
            "givenName": "Jesse",
            "gender": "female",
            "grade": 1,
            "pets": [
                { "givenName": "Goofy" },
                { "givenName": "Shadow" }
            ]
          },
          { 
            "familyName": "Miller",
             "givenName": "Lisa",
             "gender": "female",
             "grade": 8 }
      ],
      "address": { "state": "NY", "county": "Manhattan", "city": "NY" },
      "creationDate": 1431620462,
      "isRegistered": false
    }
    
    
  ###### query Andeerson family data 
  
          SELECT *
        FROM Families f
        WHERE f.id = "AndersenFamily"
        
  #### Results
  
      [{
            "id": "AndersenFamily",
            "lastName": "Andersen",
            "parents": [
               { "firstName": "Thomas" },
               { "firstName": "Mary Kay"}
            ],
            "children": [
               {
                   "firstName": "Henriette Thaulow", "gender": "female", "grade": 5,
                   "pets": [{ "givenName": "Fluffy" }]
               }
            ],
            "address": { "state": "WA", "county": "King", "city": "Seattle" },
            "creationDate": 1431620472,
            "isRegistered": true
        }]
        
##### QUERY for name city column

    SELECT {"Name":f.id, "City":f.address.city} AS Family
        FROM Families f
        WHERE f.address.city = f.address.state
#### Results

    [{
            "Family": {
                "Name": "WakefieldFamily",
                "City": "NY"
            }
        }]
        
 
