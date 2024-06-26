# BookManagement

BookManagement is an ASP.NET Core-based online book management system that allows users to add, view, edit, and delete books. The system also provides user registration and login functionality with JWT authentication.

## Features

- User registration and login
- JWT authentication
- Book management (CRUD operations)
- Role and permission management
- Swagger for API documentation

## Prerequisites

- [.NET 6 SDK](https://dotnet.microsoft.com/download/dotnet/6.0)
- [MySQL](https://www.mysql.com/downloads/)
- [Node.js and npm (for frontend development)](https://nodejs.org/)

## Setup

### Clone the repository

```sh
git clone https://github.com/yourusername/BookManagement.git
cd BookManagement
```

### Configure the database
Ensure your MySQL server is running and create a database:
```sql
CREATE DATABASE BookManagementDB;
```

Configure the database connection string in the appsettings.json file:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Database=BookManagementDB;User=root;Password=yourpassword;"
}
```

### Install dependencies
```sh
dotnet restore
```

### Add database migrations and update the database
```sh
dotnet ef migrations add InitialCreate
dotnet ef database update
```

### Run the project
```sh
Run the project
```

## Usage
### API Endpoints

- POST /api/auth/register - User registration
- POST /api/auth/login - User login
- GET /api/books - Get all books
- GET /api/books/{id} - Get a specific book by ID
- POST /api/books - Add a new book (admin only)
- PUT /api/books/{id} - Update a book by ID (admin only)
- DELETE /api/books/{id} - Delete a book by ID (admin only)

### Example Requests
User Registration
```sh
curl -X POST "http://localhost:5000/api/auth/register" -H "Content-Type: application/json" -d '{"username": "testuser", "password": "password123", "role": "User"}'
```
User Login
```sh
curl -X POST "http://localhost:5000/api/auth/login" -H "Content-Type: application/json" -d '{"username": "testuser", "password": "password123"}'
```
Get All Books
```sh
curl -X GET "http://localhost:5000/api/books" -H "Authorization: Bearer {your_jwt_token}"
```
