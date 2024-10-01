# Health&Med Authentication Service - Hackathon Project

## Overview

This project is part of the Health&Med Hackathon and focuses on handling the authentication of both doctors and patients. Built in .NET Core, the Authentication Service provides secure login functionality using JWT tokens for session management.

### Main Objective
To offer a secure authentication mechanism that supports both doctors and patients, allowing them to log in and perform authorized actions in the system.

### Key Features
- JWT-based authentication for doctors and patients
- Secure login with email and password
- Token-based authorization for API access

## Functional Requirements
1. **Login for Doctors and Patients**
   - Users (both doctors and patients) can log in using their registered Email and Password. The system responds with a JWT token for session management.
   
2. **JWT Token Generation**
   - The system generates a JWT token after successful login, which is used to authenticate subsequent requests.

3. **Token Validation**
   - Each request from a logged-in user must include a valid JWT token for authorization.

## Non-Functional Requirements
1. **Security**
   - Passwords are securely hashed, and all sensitive user data is protected. JWT tokens are securely signed.
   
2. **Scalability**
   - The service supports multiple concurrent login requests and can handle a large number of sessions without performance degradation.

## Tech Stack
- **.NET Core** for backend service
- **JWT** for secure token-based authentication
- **PostgreSQL** for user data management
- **Docker** for containerization and deployment
- **FluentValidation** for input validation
- **Entity Framework Core** for data access

## Features

### 1. Login for Doctors and Patients
Both doctors and patients can log in by providing their Email and Password. The service validates the credentials, and upon successful authentication, returns a JWT token.

### 2. JWT Token Generation
Upon successful login, a JWT token is generated, containing the user's ID and role (doctor or patient). This token is used to authorize access to protected resources.

### 3. Token Validation
Each time a user makes a request to a protected API, the JWT token must be included in the request header. The system validates the token before processing the request.

### 4. Secure Password Hashing
All passwords are securely hashed using industry-standard algorithms to ensure data protection.

## Setup & Installation

### Prerequisites
- .NET 8 SDK
- Docker & Docker Compose
- PostgreSQL

### Steps to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/hackathon-POSTECH/AuthenticationService.git
   ```

2. **Set up environment variables:**
   Create a `.env` file based on the provided `.env.example` file, and configure PostgreSQL settings.

3. **Run the application using Docker Compose:**
   ```bash
   docker-compose up --build
   ```

4. **Database migration:**
   After the containers are up, run the database migrations:
   ```bash
   dotnet ef database update
   ```

5. **Access the API:**
   The API will be accessible at `http://localhost:5000`.

## CI/CD Pipeline
The project is integrated with a CI/CD pipeline for automated testing, builds, and deployment. Tools like GitHub Actions ensure continuous integration.

## Testing
Unit tests cover the core authentication flow, including login, token generation, and token validation.

Run the tests:
```bash
dotnet test
```

## Contributors
- Health&Med Hackathon Team (FIAP SOAT students)

## License
This project is licensed under the MIT License.
