## Telegraph Express.js SDK
```
import BackendSDK from "./backend-sdk/src/index.ts";
const telegraph = new BackendSDK(secretKey, httpGateway);
```
Enter your `secretKey` and `httpGateway` from the Telegraph CDK deployment.

## Usage

All `telegraph` methods return a Promise that will resolve to the response.

## Send a Notification
```
telegraph.send(user_id, message);
```
  - `user_id` _(string, required)_: The unique identifier of the user receiving the notification.
  - `message` _(string, required)_: The message to be sent to the user.

**Response:**
  - **Success (200 OK)**: Returns a JSON object with the status code and a success message.
    - Example:
      ```json
      {
        "status": 200,
        "responseMessage": {
          "success": true,
          "message": "Notification sent successfully"
        }
      }
      ```
  - **Error (400 Bad Request)**: Returns an error message if the request fails.
    - Example:
      ```json
      {
        "status": 400,
        "message": "error"
      }
      ```

## Add User
```
telegraph.addUser(id, name, email);
```
  - `id` _(string, required)_: The unique identifier of the user.
  - `name` _(string, required)_: The full name of the user.
  - `email` _(string, required)_: The email address of the user.

**Response:**
  - **Success (200 OK)**: Returns a JSON object with the status code and a success message.
    - Example:
      ```json
      {
        "status": 200,
        "message": "User added successfully"
      }
      ```
  - **Error (400 Bad Request)**: Returns an error message if the request fails.
    - Example:
      ```json
      {
        "status": 400,
        "message": "error"
      }
      ```

## Edit User
```
telegraph.editUser(id, name, email);
```
  - `id` _(string, required)_: The unique identifier of the user.
  - `name` _(string, required)_: The updated full name of the user.
  - `email` _(string, required)_: The updated email address of the user.

**Response:**
  - **Success (200 OK)**: Returns a JSON object with the status code and a success message.
    - Example:
      ```json
      {
        "status": 200,
        "message": "User updated successfully"
      }
      ```
  - **Error (400 Bad Request)**: Returns an error message if the request fails.
    - Example:
      ```json
      {
        "status": 400,
        "message": "error"
      }
      ```

## Delete User
```
telegraph.deleteUser(id);
```
  - `id` _(string, required)_: The unique identifier of the user to be deleted.

**Response:**
  - **Success (200 OK)**: Returns a JSON object with the status code and a success message.
    - Example:
      ```json
      {
        "status": 200,
        "message": "User deleted successfully"
      }
      ```
  - **Error (400 Bad Request)**: Returns an error message if the request fails.
    - Example:
      ```json
      {
        "status": 400,
        "message": "error"
      }
      ```

## Get User
```
telegraph.getUser(id);
```
  - `id` _(string, required)_: The unique identifier of the user to retrieve.

**Response:**
  - **Success (200 OK)**: Returns a JSON object containing the user's details.
    - Example:
      ```json
      {
        "status": 200,
        "message": {
          "id": "12345",
          "name": "John Doe",
          "email": "john.doe@example.com"
        }
      }
      ```
  - **Error (404 Not Found)**: If the user is not found.
    - Example:
      ```json
      {
        "status": 404,
        "message": "User not found"
      }
      ```
  - **Error (400 Bad Request)**: If there is an error with the request.
    - Example:
      ```json
      {
        "status": 400,
        "message": "error"
      }
      ```
