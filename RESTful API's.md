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

GET Request
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