# Petstore API reference guide
Petstore provides an API that allows you to:
- Query the pet inventory
- Add a new pet to the system
- Find a pet purchase request

This document shows you how to add pet data.

## Adding a new pet
This service allows users to enter new pet data into the system.
|Service: |Method: | Request URL                        
-----------|--------|------
|`/pet`    |POST    | https://petstore.swagger.io/v2/pet       
       
 #### Request parameters:
The `Body` object includes the following parameters:
|Parameter: |Type:           | Description
------------|----------------|----------
|  id       |integer($int64) |ID number of the new pet. 
category    |{ }             |Contains the `id` and `name` parameters of the pet category.            
|  - id     |integer($int64) |ID number of the category.
|  - name   |string          |Category name.     
|name       |string          |Name of the new pet.
|photoUrls  |string          |Picture URL of the new pet.
|tags       |{ }             |Contains the `id` and `name` parameters of the pet label.
|  - id     |integer($int64) |ID number of the label.
|  - name   |string          |Label name.    
|status     |string          |Pet status (available, pending, sold).

#### Example of a request body:
`{
    "id": 12347,
    "category": {
        "id": 1,
        "name": "none"
    },
    "name": "doggie",
    "photoUrls": [
        "https://petstore.swagger.io/v2/pet/01/uploadImage"
    ],
    "tags": [
        {
            "id": 12347,
            "name": "doggie"
        }
    ],
    "status": "available"
}`
 #### Response type:
 `application/json`
 #### Response codes:
- Code 200: Successful registration.
- Code 405: Unsuccesful registration. One or more parameters are invalid.
 
## Step by step for entering pet data using Postman:
These instructions show you how to enter new pet data using the Postman console.
___
> **&#9432;** **Note** You can also use these instructions in other API development consoles of your choice, but some specific options may vary.
___
1. Open the Postman application.
2. On the URL bar, select the **POST** method.
3. On the URL bar, enter the following request URL: https://petstore.swagger.io/v2/pet
4. Click on the **body** tab.
5. Select **raw**.
6. From the drop-down menu, select **JSON**.
7. In the text field, enter the request body in JSON format as shown in the [example](#example-of-a-request-body).
8. Click **Send**.
9. The expected result is `Status: 200 OK` with a JSON that includes the same pet data within the response body.
