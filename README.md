# 👥 People Management System API

A RESTful API built using **Node.js** and **MongoDB** to manage people records, supporting full CRUD operations with proper validation, error handling, and timestamp tracking.

---

## 🌐 Live Demo

👉 [https://people-management-backend-2r5c.onrender.com/](https://people-management-backend-2r5c.onrender.com/)

---

## 🚀 Features

- ✅ Create, Read, Update, Delete (CRUD) operations  
- ✅ Input validation with clear error messaging  
- ✅ MongoDB integration with Mongoose  
- ✅ CORS enabled  
- ✅ Environment variable support via `.env`  
- ✅ Automatic timestamps (`createdAt`, `updatedAt`)  
- ✅ Well-structured and modular codebase

---

## 📦 Prerequisites

- **Node.js** (v12 or higher)  
- **MongoDB** (v4.4 or higher)  
- **npm** (Node Package Manager)

---

## ⚙️ Installation

### 1. Clone the repository
```bash
git clone https://github.com/amansaroj9616/People-Management-Backend
cd People-Management-Backend
```

### 2. Install dependencies
```bash
npm install
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory and add:
```env
PORT=3000
MONGODB_URI=mongodb://localhost:27017/people_management
```

---

## ▶️ Running the Application

### Start MongoDB (make sure MongoDB is running locally)

### Development Mode
```bash
npm run dev
```

### Production Mode
```bash
npm start
```

Server will be live at: **http://localhost:3000**

---

## 📘 API Documentation

### 🔹 1. Get All People
- **URL**: `/person`  
- **Method**: `GET`  
- **Response**:
```json
[
  {
    "_id": "60d21b4667d0d8992e610c85",
    "name": "John Doe",
    "age": 30,
    "gender": "Male",
    "mobileNumber": "1234567890",
    "createdAt": "2023-07-20T10:00:00.000Z",
    "updatedAt": "2023-07-20T10:00:00.000Z"
  }
]
```

### 🔹 2. Create a Person
- **URL**: `/person`  
- **Method**: `POST`  
- **Request Body**:
```json
{
  "name": "John Doe",
  "age": 30,
  "gender": "Male",
  "mobileNumber": "1234567890"
}
```
- **Response**:
```json
{
  "_id": "60d21b4667d0d8992e610c85",
  "name": "John Doe",
  "age": 30,
  "gender": "Male",
  "mobileNumber": "1234567890",
  "createdAt": "2023-07-20T10:00:00.000Z",
  "updatedAt": "2023-07-20T10:00:00.000Z"
}
```

### 🔹 3. Update a Person
- **URL**: `/person/:id`  
- **Method**: `PUT`  
- **Request Body**:
```json
{
  "name": "John Updated",
  "age": 31
}
```
- **Response**:
```json
{
  "_id": "60d21b4667d0d8992e610c85",
  "name": "John Updated",
  "age": 31,
  "gender": "Male",
  "mobileNumber": "1234567890",
  "createdAt": "2023-07-20T10:00:00.000Z",
  "updatedAt": "2023-07-20T10:30:00.000Z"
}
```

### 🔹 4. Delete a Person
- **URL**: `/person/:id`  
- **Method**: `DELETE`  
- **Response**:
```json
{
  "message": "Person deleted successfully"
}
```

---

## 🧠 Data Model: `Person`

| Field         | Type    | Description                        |
|---------------|---------|------------------------------------|
| name          | String  | Required. Full name of the person. |
| age           | Number  | Required. Minimum: 0               |
| gender        | String  | Required. Enum: Male/Female/Other  |
| mobileNumber  | String  | Required. 10-digit mobile number   |
| createdAt     | Date    | Auto-generated timestamp           |
| updatedAt     | Date    | Auto-generated timestamp           |

---

## ❌ Error Handling

Returns appropriate HTTP status codes:

| Status Code | Meaning               |
|-------------|------------------------|
| 200         | Success                |
| 201         | Created                |
| 400         | Bad Request            |
| 404         | Not Found              |
| 500         | Internal Server Error  |

**Example Error Response**:
```json
{
  "message": "Error message details"
}
```

---

## 🧪 Testing the API

Use [Postman](https://www.postman.com/), [Insomnia](https://insomnia.rest/), or `cURL`.

### Example using `cURL`:

- **Get all people**:
```bash
curl http://localhost:3000/person
```

- **Create a person**:
```bash
curl -X POST http://localhost:3000/person -H "Content-Type: application/json" -d '{"name":"John Doe","age":30,"gender":"Male","mobileNumber":"1234567890"}'
```

- **Update a person**:
```bash
curl -X PUT http://localhost:3000/person/<id> -H "Content-Type: application/json" -d '{"name":"John Updated","age":31}'
```

- **Delete a person**:
```bash
curl -X DELETE http://localhost:3000/person/<id>
```

---

## 🗂 Project Structure

```
people_management_backend/
├── models/
│   └── person.model.js
├── routes/
│   └── person.routes.js
├── .env
├── index.js
├── package.json
└── README.md
```
## 📄 License

This project is licensed under the **ISC License**.

---

> Made with ❤️ by Aman Saroj  and contributors
