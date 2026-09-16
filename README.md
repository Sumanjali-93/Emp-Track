# EmpTrack – Employee Management System

EmpTrack is a full-stack Employee Management System that provides a simple and efficient interface to manage employee records.
The application follows a client-server architecture where the React frontend communicates with a Spring Boot REST API, while employee data is persisted in a MySQL database.
 
---
 ## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [REST API Endpoints](#-rest-api-endpoints)
- [Getting Started](#-getting-started)
- [Backend Setup](#-backend-setup)
- [Frontend Setup](#-frontend-setup)
- [Database Configuration](#-database-configuration)
- [Application Flow](#-application-flow)
- [Future Enhancements](#-future-enhancements)

  ---

  ## 🚀 Overview

EmpTrack is a basic Employee Management System designed to demonstrate full-stack application development using modern Java and JavaScript technologies.

The system allows users to:

- View all employees
- Add new employees
- View employee details
- Update employee information
- Delete employees

The backend exposes RESTful APIs using Spring Boot, while the frontend provides a responsive user interface using React and Bootstrap.

---

## ✨ Features

### Employee Management

- Create a new employee
- View all employees
- View employee by ID
- Update employee details
- Delete an employee
- Email uniqueness validation at the database level

### Frontend

- Responsive user interface
- Employee listing
- Add employee form
- Edit employee form
- Navigation between pages
- REST API integration using Axios
- Client-side routing using React Router
- Bootstrap-based UI components

### Backend

- RESTful API architecture
- Spring Boot application
- Layered architecture
- DTO-based data transfer
- JPA/Hibernate for database operations
- MySQL database integration
- CORS configuration for frontend communication
- CRUD operations

---

## 🛠️ Tech Stack

### Backend

| Technology | Purpose |
|---|---|
| Java | Programming Language |
| Spring Boot | Backend Framework |
| Spring Web | REST API Development |
| Spring Data JPA | Data Access Layer |
| Maven | Dependency Management & Build |
| Lombok | Boilerplate Code Reduction |
| MySQL | Relational Database |

### Frontend

| Technology | Purpose |
|---|---|
| React.js | Frontend Library |
| JavaScript (ES6+) | Programming Language |
| React Router | Client-side Routing |
| Axios | HTTP Client |
| Bootstrap | Responsive UI |
| Vite | Frontend Build Tool |
| HTML5 | Structure |
| CSS3 | Styling |

---

## 📁 Project Structure

```text

EmpTrack/
│
├── backend/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/suma/ems_backend/
│   │   │   │       ├── controller/
│   │   │   │       ├── dto/
│   │   │   │       ├── entity/
│   │   │   │       ├── exception/
│   │   │   │       ├── repository/
│   │   │   │       └── service/
│   │   │   │
│   │   │   └── resources/
│   │   │       └── application.properties
│   │   │
│   │   └── test/
│   │
│   ├── pom.xml
│   └── mvnw
│
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── components/
│   │   ├── App.jsx
│   │   └── main.jsx
│   │
│   ├── package.json
│   └── vite.config.js
│
├── .gitignore
└── README.md
🔗 REST API Endpoints

Base URL:

http://localhost:8080/api/employees
Method	Endpoint	Description
GET	/api/employees	Get all employees
GET	/api/employees/{id}	Get employee by ID
POST	/api/employees	Create a new employee
PUT	/api/employees/{id}	Update an employee
DELETE	/api/employees/{id}	Delete an employee
1. Get All Employees
GET /api/employees

Returns a list of all employees.

2. Get Employee By ID
GET /api/employees/{id}

Example:

GET /api/employees/1
3. Create Employee
POST /api/employees

Request body:

{
  "firstName": "Suma",
  "lastName": "Anjali",
  "email": "suma@gmail.com"
}
4. Update Employee
PUT /api/employees/{id}

Example:

PUT /api/employees/1

Request body:

{
  "firstName": "Suma",
  "lastName": "Anjali",
  "email": "suma@gmail.com"
}
5. Delete Employee
DELETE /api/employees/{id}

Example:

DELETE /api/employees/1

Response:

Employee deleted successfully
⚙️ Getting Started

Follow these steps to run EmpTrack locally.

Prerequisites

Make sure the following are installed:

Java 17 or later
Maven
MySQL
Node.js
npm
Git
🔧 Backend Setup
1. Clone the Repository
git clone https://github.com/Sumanjali-93/EmpTrack.git

Navigate to the project:

cd EmpTrack
2. Navigate to Backend
cd backend
3. Configure MySQL

Create a MySQL database:

CREATE DATABASE ems;

Configure your database credentials in:

backend/src/main/resources/application.properties

Example:

spring.datasource.url=jdbc:mysql://localhost:3306/ems
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

Note: Do not commit database credentials or other sensitive configuration to GitHub.

4. Run the Backend

Using Maven:

mvn spring-boot:run

Or using the Maven wrapper on Windows:

mvnw.cmd spring-boot:run

The backend will run on:

http://localhost:8080
💻 Frontend Setup

Open a new terminal and navigate to the frontend:

cd frontend

Install dependencies:

npm install

Start the development server:

npm run dev

The frontend will be available at:

http://localhost:3000

The port may change if the default port is already in use.

🗄️ Database Configuration

EmpTrack uses MySQL as the relational database.

The backend uses:

Spring Data JPA
        ↓
     Hibernate
        ↓
       MySQL

Employee information is stored in the database and managed through JPA repositories.

🔄 Application Flow
        React Frontend
              │
              │ Axios HTTP Requests
              ▼
       Spring Boot REST API
              │
              │ Service Layer
              ▼
        Repository Layer
              │
              │ JPA / Hibernate
              ▼
            MySQL

Example:

User
  ↓
React Employee Form
  ↓
Axios POST Request
  ↓
Spring Boot Controller
  ↓
Employee Service
  ↓
Employee Repository
  ↓
MySQL Database
🧭 Frontend Routes
Route	Description
/	Employee List
/employees	Employee List
/add-employee	Add Employee
/edit-employee/:id	Edit Employee
🔒 Security

Database credentials are kept outside the source-controlled configuration using .gitignore.

The following file is excluded from Git:

backend/src/main/resources/application.properties

This prevents sensitive database credentials from being accidentally pushed to the public repository.

🔮 Future Enhancements

Potential improvements for future versions include:

User authentication and authorization
Spring Security with JWT
Employee search and filtering
Pagination and sorting
Employee profile management
Form validation
Global exception handling
Unit and integration testing
API documentation with Swagger/OpenAPI
Docker containerization
Cloud deployment
Role-based access control
