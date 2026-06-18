Mini Pro 4 – Task Management API
Description

Mini Pro 4 is a REST API built with Node.js, Express, MongoDB, and JWT authentication.

The application allows users to:

Register an account
Log in using email and password
Create tasks
View their tasks
Update tasks
Delete tasks
Filter tasks by status and creation date

Each task belongs to a specific user, and users can only access their own tasks.

Technologies
Node.js
Express.js
MongoDB
Mongoose
JWT (JSON Web Token)
bcrypt
dotenv
Project Structure
mini_pro4/
│
├── controllers/
│   ├── authController.js
│   └── taskController.js
│
├── middleware/
│   └── authMiddleware.js
│
├── models/
│   ├── User.js
│   └── Task.js
│
├── routes/
│   ├── auth.js
│   └── task.js
│
├── .env
├── server.js
├── package.json
└── README.md
Installation

Clone the repository:

git clone <repository-url>

Install dependencies:

npm install

Create a .env file:

PORT=3333
MONGO_URI=mongodb://localhost:27017/mini_pro4
JWT_SECRET=your_secret_key

Start the server:

npm start

or

nodemon server.js
Authentication
Register User

POST

/auth/register

Request body:

{
  "name": "Larysa",
  "email": "larysa@test.com",
  "password": "123456"
}

Response:

{
  "message": "User registered successfully"
}
Login User

POST

/auth/login

Request body:

{
  "email": "larysa@test.com",
  "password": "123456"
}

Response:

{
  "token": "jwt_token"
}
Authorization

Protected routes require a JWT token.

Header:

Authorization: Bearer YOUR_TOKEN
Task Endpoints
Create Task

POST

/tasks

Request body:

{
  "title": "Learn JWT",
  "description": "Create authentication middleware",
  "status": "in progress"
}
Get All Tasks

GET

/tasks
Filter by Status
/tasks?status=completed

or

/tasks?status=in progress
Filter by Date
/tasks?startDate=2025-01-01
/tasks?endDate=2025-12-31
/tasks?startDate=2025-01-01&endDate=2025-12-31
Update Task

PUT

/tasks/:id

Example:

/tasks/6860f4d2d2f1f54e6b3a2c1f

Request body:

{
  "status": "completed"
}
Delete Task

DELETE

/tasks/:id

Example:

/tasks/6860f4d2d2f1f54e6b3a2c1f
Security Features
Password hashing using bcrypt
JWT authentication
Protected routes
User-specific task access
Unauthorized requests return HTTP 401
Future Improvements
Input validation
Refresh Tokens
Pagination
Sorting
Error handling middleware
Role-based authorization
CORS configuration
Author

Larysa Sperling

Node.js & MongoDB Learning Project
