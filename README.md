# Taskify

Taskify is a robust and efficient task management application built with modern web technologies. It allows users to manage their tasks seamlessly, including features such as task creation, updating, deletion, and status tracking.

---

## Features

- **Create Tasks:** Add new tasks with relevant details.
- **Update Tasks:** Modify existing task information.
- **Delete Tasks:** Remove tasks when completed or unnecessary.
- **Track Task Status:** Mark tasks as completed or pending.

---

## Technologies Used

- **Frontend:** React.js
- **Backend:** Node.js, Express.js
- **Database:** MongoDB
- **Authentication:** JWT (JSON Web Tokens)

---

## Prerequisites

Ensure you have the following installed:

- **Node.js** (v14 or later)
- **MongoDB** (running locally or on a cloud service like MongoDB Atlas)

---

## Installation and Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/priyaanshusoni/Taskify.git
   cd Taskify
   ```

2. **Install dependencies:**
   ```bash
   # For backend
   cd backend
   npm install

   # For frontend
   cd ../frontend
   npm install
   ```

3. **Set up environment variables:**
   Create a `.env` file in the `backend` directory with the following variables:
   ```env
   PORT=5000
   MONGO_URI=<your-mongodb-connection-string>
   JWT_SECRET=<your-secret-key>
   ```

4. **Start the application:**
   ```bash
   # Start backend
   cd backend
   npm start

   # Start frontend
   cd ../frontend
   npm start
   ```

5. **Access the application:**
   Open your browser and navigate to `http://localhost:3000`.

---

## API Endpoints

### Base URL

```
http://localhost:5000/api
```

### Authentication

#### 1. **Register User**
- **Endpoint:** `POST /auth/register`
- **Description:** Registers a new user.
- **Request Body:**
  ```json
  {
    "name": "John Doe",
    "email": "john@example.com",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "message": "User registered successfully",
    "token": "<JWT-token>"
  }
  ```

#### 2. **Login User**
- **Endpoint:** `POST /auth/login`
- **Description:** Logs in an existing user.
- **Request Body:**
  ```json
  {
    "email": "john@example.com",
    "password": "password123"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Login successful",
    "token": "<JWT-token>"
  }
  ```

---

### Tasks

#### 1. **Get All Tasks**
- **Endpoint:** `GET /tasks`
- **Description:** Fetches all tasks for the authenticated user.
- **Headers:**
  ```json
  {
    "Authorization": "Bearer <JWT-token>"
  }
  ```
- **Response:**
  ```json
  [
    {
      "_id": "task-id",
      "title": "Task 1",
      "description": "Task description",
      "status": "pending",
      "createdAt": "2025-01-01T00:00:00Z",
      "updatedAt": "2025-01-02T00:00:00Z"
    }
  ]
  ```

#### 2. **Create Task**
- **Endpoint:** `POST /tasks`
- **Description:** Creates a new task.
- **Headers:**
  ```json
  {
    "Authorization": "Bearer <JWT-token>"
  }
  ```
- **Request Body:**
  ```json
  {
    "title": "New Task",
    "description": "Task details"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Task created successfully",
    "task": {
      "_id": "task-id",
      "title": "New Task",
      "description": "Task details",
      "status": "pending",
      "createdAt": "2025-01-01T00:00:00Z",
      "updatedAt": "2025-01-01T00:00:00Z"
    }
  }
  ```

#### 3. **Update Task**
- **Endpoint:** `PUT /tasks/:id`
- **Description:** Updates an existing task.
- **Headers:**
  ```json
  {
    "Authorization": "Bearer <JWT-token>"
  }
  ```
- **Request Body:**
  ```json
  {
    "title": "Updated Task",
    "description": "Updated details",
    "status": "completed"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Task updated successfully",
    "task": {
      "_id": "task-id",
      "title": "Updated Task",
      "description": "Updated details",
      "status": "completed",
      "createdAt": "2025-01-01T00:00:00Z",
      "updatedAt": "2025-01-02T00:00:00Z"
    }
  }
  ```

#### 4. **Delete Task**
- **Endpoint:** `DELETE /tasks/:id`
- **Description:** Deletes a task by ID.
- **Headers:**
  ```json
  {
    "Authorization": "Bearer <JWT-token>"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Task deleted successfully"
  }
  ```

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request for review.

---

## Contact

For questions or support, feel free to reach out:
- **Author:** Priyaanshu Soni
- **GitHub:** [priyaanshusoni](https://github.com/priyaanshusoni)

