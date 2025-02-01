---
tags:
  - braindump
  - javascript
created: 2025-01-31T18:58:00
---
REST - Representational State Transfer 

Essentially REST APIs are API's with a particular set of protocols and rules. The jist of an API (application programming interface) is to request and respond with data. REST API's use HTTP methods like GET, POST, PUT, DELETE.

This group of methods is also known as CRUD (Create, Read, Update, Delete).

# Making HTTP Requests 
To make a request to a REST API, you utilize an endpoint, which a URL that directs your request. Note that you specify the HTTP method in the request by adding it to the fetch API method. GET is the implied value, so if you were to omit the HTTP method entirely, GET would be used by default.
****
GET request
```javascript
async function GetData() {
  let endpoint = 'https://jsonplaceholder.typicode.com/users';
  const request = await fetch(endpoint, { method: 'GET' });
  const response = await request.json();
  console.log(response);
}
GetData(); // call the function
```
POST request
```javascript
async function AddData() {
  let endpoint = 'https://jsonplaceholder.typicode.com/users';
  const request = await fetch(endpoint, {
    method: 'POST',
    body: JSON.stringify(data),
  });
  
  const response = await request.json();
  console.log(response);
}
const data = { username: 'John Snow', age: 22 };

AddData(); // call the function
```
PUT request
```javascript
async function UpdateData() {
  let endpoint = 'https://jsonplaceholder.typicode.com/users/2';
  const request = await fetch(endpoint, {
    method: 'PUT',
    body: JSON.stringify(data),
  });

  const response = await request.json();
  console.log(response);
}

const data = { age: 42 }; // update the age

UpdateData(); // call the function
```
DELETE Request
```javascript
async function UpdateData() {
  let endpoint = 'https://jsonplaceholder.typicode.com/users/2';
  const request = await fetch(endpoint, { method: 'DELETE' });

  const response = await request.json();
  console.log(response);
}

UpdateData(); // call the function
```

When you make requests, youre typically expecting to receive some kind of data back. If you look at the examples of making requests above, you'll notice that data is located in the body of the request. The response variable uses the request.json() method to parse the requests body and return the data into an object we can use for our app. 

Before you go an start working with the data though, you want to make sure that the request was successful. This is where [[HTTP Status Codes]] come in.

```javascript
async function GetData() {
  let endpoint = 'https://jsonplaceholder.typicode.com/users';
  const request = await fetch(endpoint, { method: 'GET' });
  const response = await request.json();

  if (request.status == 200) {
    // Request was successful
    console.log(request.status);
  }
}

GetData(); // call the function
```