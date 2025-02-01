---
tags:
  - braindump
  - javascript
created: 2025-01-31T18:58:00
---
REST - Representational State Transfer 

Essentially REST APIs are API's with a particular set of protocols and rules. The jist of an API (application programming interface) is to request and respond with data. REST API's use HTTP methods like GET, POST, PUT, DELETE.

This group of methods is also known as CRUD (Create, Read, Update, Delete).

```javascript

//GET request
async function GetData() {
  let endpoint = 'https://jsonplaceholder.typicode.com/users';
  const request = await fetch(endpoint, { method: 'GET' });
  const response = await request.json();
  console.log(response);
}
GetData(); // call the function
//POST request
```


