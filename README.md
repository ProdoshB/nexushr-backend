# NexusHR Backend

A Spring Boot REST API for managing employee records, built as part of the Zidio Development Java Full Stack Developer Internship.

## Overview

This is a backend-focused slice of the larger "NexusHR – AI-Enabled Enterprise HR & Workforce Intelligence Platform" concept, scoped to a realistic, fully working core: employee CRUD operations backed by a MySQL database. Larger features in the original project vision (AI attrition prediction, Kubernetes deployment, microservices, Spring AI, etc.) are documented as future scope rather than implemented, given the project timeline.

## Tech Stack

- Java 21
- Spring Boot 4.1.1
- Spring Data JPA / Hibernate
- MySQL 8
- Spring Security (currently open/permitAll — JWT authentication planned as a next step)
- Lombok
- Maven

## Architecture

Standard layered architecture:

Controller -> Service -> Repository -> Entity -> MySQL

- entity/Employee.java — JPA entity mapping to the employees table
- repository/EmployeeRepository.java — Spring Data JPA repository
- service/EmployeeService.java — business logic layer
- controller/EmployeeController.java — REST API endpoints
- config/SecurityConfig.java — Spring Security configuration

## API Endpoints

| Method | Endpoint              | Description             |
|--------|------------------------|--------------------------|
| POST   | /api/employees         | Create a new employee   |
| GET    | /api/employees         | Get all employees       |
| GET    | /api/employees/{id}    | Get employee by ID      |
| PUT    | /api/employees/{id}    | Update employee by ID   |
| DELETE | /api/employees/{id}    | Delete employee by ID   |

## Running Locally

1. Create a MySQL database named hr_management
2. Update credentials in src/main/resources/application.properties if different from defaults
3. Run NexushrApplication.java
4. Test endpoints using Postman at http://localhost:8080/api/employees

## Future Scope

- JWT-based authentication and role-based access (Employee/Manager/HR)
- Additional modules: Leave management, Attendance, Payroll
- Frontend integration (React)
- Cloud deployment
- AI-driven analytics (attrition prediction, workforce insights)

## Author

Prodosh Bhattacharya — Java Full Stack Developer Intern, Zidio Development