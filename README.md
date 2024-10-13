# Petstore
Test Pet CRUD

Test cases for GET /pet/{petId} “Find pet by ID” endpoint

1) Check request with valid existing ID<br/>
**Preconditions**: Make sure that Pet with this ID exists, for example send request POST /pet to create it or check db<br/>
**Steps:**<br/>
Send request with random valid existing ID (int64)<br/>
**Expected result:**<br/>
Status code 200 OK<br/>
ID in response is equal to ID from request<br/>
Response body has all the fields that Pet object has<br/> 
2) Check request with valid non-existent ID<br/>
**Preconditions:** Make sure that Pet with this ID doesn't exist, for example send request DELETE /pet to delete it or check db<br/>
**Steps:**<br/>
Send request with random valid non-existent ID (int64)<br/>
**Expected result:**<br/>
Status code 404 Not Found<br/>
Response body has the message that Pet is not found<br/>
3) Check request with negative input<br/>
**Steps:**<br/>
Send request with random negative input<br/>
**Expected result:**<br/>
Status code 400 Bad Request<br/>
Response body has the message about invalid ID format<br/>
4) Check request with too big input<br/>
**Steps:**<br/>
Send request with random number that is bigger than int64 Maximum<br/>
**Expected result:**<br/>
Status code 400 Bad Request<br/>
Response body has the message about invalid ID format<br/>
5) Check request with string input<br/>
**Steps:**<br/>
Send request with random string<br/>
**Expected result:**<br/>
Status code 400 Bad Request<br/>
Response body has the message about invalid ID format<br/>
6) Check request with special characters in input<br/>
**Steps:**<br/>
Send request with random special characters (for example !@#$%^*) in input<br/>
**Expected result:**<br/>
Status code 400 Bad Request<br/>
Response body has the message about invalid ID format<br/>
7) Check request with empty input<br/>
**Steps:**<br/>
Send request with empty input<br/>
**Expected result:**<br/>
Status code 400 Bad Request<br/>
Response body has the message that required field is not provided<br/>
8) Perfomance test<br/> 
**Steps:**<br/>
Send many request with different IDs<br/>
**Expected result:**<br/>
Status codes according to requests (200, 400, 404)<br/>
The server responds without delays or errors<br/>
