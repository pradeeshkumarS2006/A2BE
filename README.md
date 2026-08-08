# A2BE

# Task API

A RESTful Task Management API built using **Node.js, Express.js, and PostgreSQL**. The API supports creating, reading, updating, and deleting tasks through standard HTTP methods.

## 🚀 Features

* REST API using Express.js
* PostgreSQL database integration
* CRUD operations for tasks
* Get all tasks
* Get a task by ID
* Create a new task
* Update an existing task
* Delete a task
* Health-check endpoint
* Environment variables using `.env`
* PostgreSQL running with Docker Compose

## 🛠️ Technologies Used

* Node.js
* Express.js
* PostgreSQL
* `pg` — PostgreSQL client for Node.js
* dotenv
* Docker
* Docker Compose

## 📁 Project Structure

```text
task-api/
│
├── server.js
├── db.js
├── init.sql
├── docker-compose.yml
├── package.json
├── package-lock.json
├── .env
├── .env.example
├── .gitignore
└── README.md
```

## ⚙️ Setup

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd task-api
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file:

```env
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=your_password
DB_NAME=taskdb
```

Do not upload `.env` to GitHub.

### 4. Start PostgreSQL with Docker

Make sure Docker Desktop is running.

```bash
docker compose up -d
```

Check the container:

```bash
docker ps
```

The PostgreSQL container should be running on port `5432`.

### 5. Start the API

```bash
node server.js
```

The server runs at:

```text
http://localhost:5000
```

## 🔗 API Endpoints

### Health Check

```http
GET /health
```

URL:

```text
http://localhost:5000/health
```

Response:

```json
{
  "status": "ok"
}
```

### Get All Tasks

```http
GET /tasks
```

URL:

```text
http://localhost:5000/tasks
```

### Get Task by ID

```http
GET /tasks/:id
```

Example:

```text
http://localhost:5000/tasks/1
```

### Create a Task

```http
POST /tasks
```

URL:

```text
http://localhost:5000/tasks
```

Request body:

```json
{
  "title": "Complete backend assignment"
}
```

### Update a Task

```http
PUT /tasks/:id
```

Example:

```text
http://localhost:5000/tasks/1
```

Request body:

```json
{
  "title": "Complete backend assignment",
  "done": true
}
```

### Delete a Task

```http
DELETE /tasks/:id
```

Example:

```text
http://localhost:5000/tasks/1
```

No request body is required.

## 🗄️ Database

The application uses a PostgreSQL `tasks` table.

```sql
CREATE TABLE tasks (
    id SERIAL PRIMARY KEY,
    title TEXT NOT NULL,
    done BOOLEAN DEFAULT FALSE
);
```

The API uses parameterized SQL queries to interact with PostgreSQL.

## 🐳 Docker

Start PostgreSQL:

```bash
docker compose up -d
```

Stop the containers:

```bash
docker compose down
```

Check running containers:

```bash
docker ps
```

## 🧪 Testing the API

You can test the API using:

* Postman
* Thunder Client
* curl
* Browser for GET endpoints

Example:

```bash
curl http://localhost:5000/tasks
```

For `POST`, `PUT`, and `DELETE`, use Postman or Thunder Client.

## 📌 API Summary

| Method | Endpoint     | Description         |
| ------ | ------------ | ------------------- |
| GET    | `/`          | API information     |
| GET    | `/health`    | Check server status |
| GET    | `/tasks`     | Get all tasks       |
| GET    | `/tasks/:id` | Get one task        |
| POST   | `/tasks`     | Create task         |
| PUT    | `/tasks/:id` | Update task         |
| DELETE | `/tasks/:id` | Delete task         |

## 👨‍💻 Author

**Pradeesh Kumar S**

B.Sc. Computer Science Student

Backend Development • Java • JavaScript • SQL • Web Development

```
```
