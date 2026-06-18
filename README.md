# Mini Pro 4 – Task Management API

## Description

Mini Pro 4 is a REST API built with Node.js, Express, MongoDB, and JWT authentication.

The application allows users to:

- Register an account
- Log in using email and password
- Create tasks
- View their tasks
- Update tasks
- Delete tasks
- Filter tasks by status and creation date

Each task belongs to a specific user, and users can only access their own tasks.

---

## Technologies

- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT (JSON Web Token)
- bcrypt
- dotenv

---

## Project Structure

```text
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
```

---

## Installation

Install dependencies:

```bash
npm install
```

Create a `.env` file:

```env
PORT=3333
MONGO_URI=mongodb://localhost:27017/mini_pro4
JWT_SECRET=your_secret_key
```

Start the server:

```bash
npm start
```

or

```bash
nodemon server.js
```

---

## Authentication

### Register User

**POST**

```http
/auth/register
```

Request body:

```json
{
  "name": "Larysa",
  "email": "larysa@test.com",
  "password": "123456"
}
```

### Login User

**POST**

```http
/auth/login
```

Request body:

```json
{
  "email": "larysa@test.com",
  "password": "123456"
}
```

Response:

```json
{
  "token": "jwt_token"
}
```

---

## Authorization

Protected routes require a JWT token.

```http
Authorization: Bearer YOUR_TOKEN
```

---

## Task Endpoints

### Create Task

**POST**

```http
/tasks
```

Request body:

```json
{
  "title": "Learn JWT",
  "description": "Create authentication middleware",
  "status": "in progress"
}
```

---

### Get Tasks

**GET**

```http
/tasks
```

---

### Filter Tasks by Status

```http
/tasks?status=completed
```

```http
/tasks?status=in progress
```

---

### Filter Tasks by Date

```http
/tasks?startDate=2025-01-01
```

```http
/tasks?endDate=2025-12-31
```

```http
/tasks?startDate=2025-01-01&endDate=2025-12-31
```

---

### Update Task

**PUT**

```http
/tasks/:id
```

Example:

```http
/tasks/6860f4d2d2f1f54e6b3a2c1f
```

---

### Delete Task

**DELETE**

```http
/tasks/:id
```

Example:

```http
/tasks/6860f4d2d2f1f54e6b3a2c1f
```

---

## Security Features

- Password hashing with bcrypt
- JWT authentication
- Protected routes
- User-specific task access
- Unauthorized requests return HTTP 401

---

## Future Improvements

- Input validation
- Refresh Tokens
- Pagination
- Sorting
- Error handling middleware
- Role-based authorization
- CORS configuration

---

## Author

**Larysa Sperling**

Node.js & MongoDB Learning Project


