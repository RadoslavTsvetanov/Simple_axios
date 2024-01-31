*DEPENDENCIES*
 - node
 - ts-node
 - npm
*SET UP PROJECT*
npm i

*DOCS*
## `ApiClient` Usage Documentation

### Installation

First, ensure you have `axios` installed. If not, you can install it using:

```bash
npm install axios
```
Importing ApiClient

```javascript

import { ApiClient } from './path-to-api-client';
```
Creating an Instance

To use ApiClient, create an instance by providing the base URL of your API:

```javascript

const apiClient = new ApiClient("http://localhost:3000");
```
Making GET Requests

You can make GET requests using the getRequest method. Example:

```javascript

try {
  const response = await apiClient.getRequest("get/pipi", {}, undefined);
  console.log(response);
} catch (error) {
  console.error(error);
}
```
Making POST Requests

For POST requests, use the postRequest method. Example:

```javascript

try {
  const response = await apiClient.postRequest("update", { pipi: 4 }, undefined);
  console.log(response);
} catch (error) {
  console.error(error);
}
```
Static Methods

You can also use static methods directly on the ApiClient class without creating an instance:
Static GET Request

```javascript

try {
  const response = await ApiClient.staticGetRequest("http://localhost:3000/get/pipi", undefined);
  console.log(response);
} catch (error) {
  console.error(error);
}
```
Static POST Request

```javascript

try {
  const response = await ApiClient.staticPostRequest("http://localhost:3000/update", { pipi: 4 }, undefined);
  console.log(response);
} catch (error) {
  console.error(error);
}
```
Response Format

The response object has the following structure:

```javascript

{
  data: {},            // Response data
  status: 200,         // HTTP status code
  err: undefined       // Error message (if any)
}
```
Handling Responses

You can handle the responses in the try block and errors in the catch block.

javascript
```
try {
  const response = await apiClient.getRequest("get/pipi", {}, undefined);
  console.log(response.data);    // Access response data
  console.log(response.status);  // Access response status
} catch (error) {
  console.error(error.err);      // Access error message (if any)
  console.error(error.status);   // Access error status (if any)
}
```
