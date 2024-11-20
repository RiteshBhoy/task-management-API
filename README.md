Task Management API
A RESTful API for managing tasks, allowing users to perform CRUD operations and mark tasks as complete. The API also includes user authentication for secure access.

Features
User Authentication: Register and log in with secure password hashing.
Task Management: Create, read, update, and delete tasks.
Task Completion: Mark tasks as completed.
Error Handling: Comprehensive error handling for all endpoints.
Validation: Input validation to ensure data integrity.
Technologies Used
Node.js: Server-side runtime environment.
Express.js: Web framework for building RESTful APIs.
MongoDB: Database for storing user and task data.
Mongoose: ODM for MongoDB.
bcrypt.js: For password hashing.
Postman: API testing tool.
Installation
Prerequisites
Node.js (version 14 or above)
MongoDB (running locally or hosted, e.g., MongoDB Atlas)
Postman (or any API testing tool)
Steps
Clone the repository:

bash
Copy code
git clone <repository_url>  
cd task-management-api  
Install dependencies:

bash
Copy code
npm install  
Create a .env file in the root directory and add the following:

env
Copy code
PORT=5000  
MONGO_URI=mongodb://localhost:27017/task_manager  
JWT_SECRET=your_jwt_secret_key  
Start the server:

bash
Copy code
npm start  
The API will be available at http://localhost:5000/api.

API Endpoints
Authentication
POST /auth/register: Register a new user.

Request body:
json
Copy code
{  
  "username": "string",  
  "password": "string"  
}  
POST /auth/login: Log in a user.

Request body:
json
Copy code
{  
  "username": "string",  
  "password": "string"  
}  
Tasks
GET /tasks: Retrieve all tasks (authenticated).

GET /tasks/
: Retrieve a specific task by ID.

POST /tasks: Create a new task.

Request body:
json
Copy code
{  
  "title": "string",  
  "description": "string",  
  "due_date": "YYYY-MM-DD"  
}  
PUT /tasks/
: Update an existing task.

DELETE /tasks/
: Delete a task.

PATCH /tasks/
/complete: Mark a task as completed.

Testing with Postman

1) Set up an environment in Postman:

  Variable: baseUrl
  Value: http://localhost:5000/api

2) Authentication:

   Register a user with POST {{baseUrl}}/auth/register.
   Log in with POST {{baseUrl}}/auth/login to get a token.

3) Authorization:

   Copy the token from the login response.
   Add it to the Authorization header as Bearer <your_token> for subsequent requests.

4) CRUD Operations on Tasks:

    Use the token to perform tasks operations.
