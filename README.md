# Event Booking REST API

A **RESTful API for an Event Management & Registration System** built using **Go (Golang)**, **Gin Web Framework**, and **SQLite**.

The API provides user authentication, event management, and event registration functionality.

## 🚀 Features

* User Signup & Login
* Secure password hashing using **Bcrypt**
* JWT-based authentication
* Create and view events
* Update and delete events
* Event ownership authorization
* Register for events
* Cancel event registrations
* SQLite database

## 🛠️ Technologies Used

* **Go (Golang)**
* **Gin Web Framework**
* **SQLite**
* **JWT**
* **Bcrypt**
* **REST Client for VS Code**

## 📂 Project Structure

```text
event-booking-rest-api/
│
├── api-test/          # HTTP files for API testing
├── db/                # Database configuration
├── middlewares/       # Authentication middleware
├── models/            # Data models and database operations
├── routes/            # API routes and handlers
├── utils/             # JWT and password utilities
│
├── main.go            # Application entry point
├── go.mod             # Go module configuration
└── go.sum             # Dependency checksums
```

## 🌐 API Endpoints

| Method   | Endpoint               | Auth    | Description           |
| -------- | ---------------------- | ------- | --------------------- |
| `POST`   | `/signup`              | ❌       | Create a new user     |
| `POST`   | `/login`               | ❌       | Login and receive JWT |
| `GET`    | `/events`              | ❌       | Get all events        |
| `GET`    | `/events/:id`          | ❌       | Get a single event    |
| `POST`   | `/events`              | ✅       | Create an event       |
| `PUT`    | `/events/:id`          | ✅ Owner | Update an event       |
| `DELETE` | `/events/:id`          | ✅ Owner | Delete an event       |
| `POST`   | `/events/:id/register` | ✅       | Register for an event |
| `DELETE` | `/events/:id/register` | ✅       | Cancel registration   |

## 🔐 Authentication

The API uses **JWT (JSON Web Token)** for authentication.

After successful login, the server returns a JWT token. This token must be provided in the `Authorization` header when accessing protected endpoints.

```text
Authorization: <JWT_TOKEN>
```

Protected operations include creating, updating, and deleting events, as well as registering and cancelling registrations.

## 🗄️ Database

The project uses **SQLite** for data storage.

The database contains three main tables:

* `users` — Stores user information and hashed passwords.
* `events` — Stores event details and event ownership.
* `registrations` — Stores event registration information.

The database file is created as:

```text
api.db
```

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd event-booking-rest-api
```

### 2. Install dependencies

```bash
go mod download
```

### 3. Run the server

```bash
go run .
```

The API will run on:

```text
http://localhost:8080
```

## 🧪 API Testing

The `api-test/` folder contains `.http` files that can be used to test the API using the **REST Client extension in VS Code**.

## 👨‍💻 Author

**Pritam Singh**
