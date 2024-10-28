# Workout Tracker Backend

This project is a backend system for a workout tracker application developed with Spring Boot. Users can sign up, log in, create workout plans, and track their progress. Key features include JWT-based authentication, CRUD operations for workouts, and report generation.

## Table of Contents
- [Features](#features)
- [Requirements](#requirements)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [API Endpoints](#api-endpoints)
- [Database Schema](#database-schema)
- [Testing](#testing)
- [Documentation](#documentation)

---

## Features
- **User Authentication**: Users can sign up, log in, and log out.
- **JWT Authorization**: Secure API access with JSON Web Tokens (JWT).
- **Workout Management**: Create, update, delete, and view workout plans with exercises, repetitions, sets, and weights.
- **Scheduling and Reports**: Schedule workouts by date and time, and generate reports on workout progress.

## Requirements
- **Java**: Version 17 or higher.
- **Spring Boot**: Version 3.0 or higher.
- **Database**: Relational database (e.g., MySQL, PostgreSQL).
- **API Specification**: RESTful API.
- **Authentication**: JWT for securing API endpoints.
- **Testing**: JUnit and Mockito for unit testing.
- **Documentation**: OpenAPI for API specifications.

## Project Structure
```plaintext
workout-tracker-backend/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── com/example/workouttracker/
│   │   │       ├── controllers/
│   │   │       ├── models/
│   │   │       ├── repositories/
│   │   │       ├── services/
│   │   │       └── config/
│   │   └── resources/
│   │       └── application.properties
│   └── test/
│       └── java/com/example/workouttracker/
├── README.md
├── pom.xml
└── .gitignore
```

## Installation

1. Clone this repository:
    ```bash
    git clone https://github.com/yourusername/workout-tracker-backend.git
    ```

2. Navigate to the project directory:
    ```bash
    cd workout-tracker-backend
    ```

3. Configure the database connection in `src/main/resources/application.properties`:
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/workout_db
    spring.datasource.username=your_username
    spring.datasource.password=your_password
    spring.jpa.hibernate.ddl-auto=update
    jwt.secret=your_jwt_secret
    ```

4. Build and run the application:
    ```bash
    ./mvnw spring-boot:run
    ```

## Usage

### Run the Server
Start the Spring Boot server by running:
```bash
./mvnw spring-boot:run
```

The server will start on `http://localhost:8080`.

## API Endpoints

### Authentication
- **POST** `/api/auth/signup` - Sign up a new user.
- **POST** `/api/auth/login` - Log in an existing user.
- **POST** `/api/auth/logout` - Log out the user.

### Workout Management
- **POST** `/api/workouts` - Create a new workout plan.
- **GET** `/api/workouts` - List all workouts, sorted by date.
- **GET** `/api/workouts/{id}` - Get a specific workout plan by ID.
- **PUT** `/api/workouts/{id}` - Update a workout plan by ID.
- **DELETE** `/api/workouts/{id}` - Delete a workout plan by ID.

### Scheduling and Reports
- **POST** `/api/workouts/{id}/schedule` - Schedule a workout for a specific date and time.
- **GET** `/api/reports` - Generate a report on past workouts and progress.

## Database Schema
- **Users**: Stores user details, such as username, email, and password (hashed).
- **Exercises**: Stores exercise details, including name, description, and category/muscle group.
- **Workouts**: Stores workout plans, each linked to a user and a list of exercises with specific repetitions, sets, and weights.

## Testing
Run unit tests with JUnit:
```bash
./mvnw test
```

## Documentation
This project uses OpenAPI for API documentation. Access it via:
- `http://localhost:8080/swagger-ui.html` (once the server is running).

---

## License
This project is licensed under the MIT License.
```

This template provides an organized overview of your Spring Boot application. Let me know if you need additional customization for specific setup details or dependencies.
