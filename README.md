# Spring Boot Web Application - intro-spring-web

A comprehensive Spring Boot web application demonstrating different HTTP request methods, form handling, and AJAX implementation. This project serves as an educational example for learning Spring Boot web development concepts.

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Form Examples](#form-examples)
- [Technologies Used](#technologies-used)
- [Configuration](#configuration)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)

## 🎯 Overview

This Spring Boot application demonstrates fundamental web development concepts including:
- REST controller implementation
- GET and POST request handling
- Form submission with page reload
- AJAX form submission without page reload
- Static content serving
- JSON response formatting

The application provides a user-friendly interface to interact with different endpoints and understand how various HTTP methods work in a Spring Boot environment.

## ✨ Features

### Backend Features
- **RESTful API Endpoints**: Multiple endpoints demonstrating different HTTP methods
- **Parameter Handling**: Query parameters and form data processing
- **JSON Responses**: Structured JSON responses for status endpoints
- **Cross-Method Support**: Both GET and POST methods for the same endpoint

### Frontend Features
- **Modern UI**: Clean, responsive design with CSS styling
- **Form Handling**: Two different approaches to form submission
- **AJAX Integration**: Asynchronous requests without page reload
- **Interactive Elements**: Real-time feedback and error handling
- **Multiple Examples**: Side-by-side comparison of different techniques

## 📁 Project Structure

```
intro-spring-web/
├── src/
│   ├── main/
│   │   ├── java/
│   │   │   └── edu/eci/arsw/introSpring/
│   │   │       ├── App.java                    # Legacy main class
│   │   │       └── WebSiteController.java      # Main Spring Boot controller
│   │   └── resources/
│   │       ├── application.properties           # Application configuration
│   │       └── static/
│   │           └── index.html                   # Frontend interface
│   └── test/
│       └── java/
│           └── edu/eci/arsw/introSpring/
│               └── AppTest.java                 # Unit tests
├── pom.xml                                      # Maven configuration
└── README.md                                    # Project documentation
```

## 🔧 Prerequisites

Before running this application, ensure you have the following installed:

- **Java 8 or higher** (JDK 8+)
- **Maven 3.6+** for dependency management and building
- **Git** for version control (optional)
- **Web Browser** for testing the frontend interface

## 🚀 Installation

1. **Clone the repository** (if using version control):
   ```bash
   git clone https://github.com/AnderssonProgramming/intro-spring-web.git
   cd intro-spring-web
   ```

2. **Verify Java installation**:
   ```bash
   java -version
   ```

3. **Verify Maven installation**:
   ```bash
   mvn -version
   ```

4. **Install dependencies**:
   ```bash
   mvn clean install
   ```

## ▶️ Running the Application

### Method 1: Using Maven Spring Boot Plugin
```bash
mvn spring-boot:run
```

### Method 2: Using Maven to build and run JAR
```bash
mvn clean package
java -jar target/intro-spring-1.0-SNAPSHOT.jar
```

### Method 3: Direct execution from IDE
Run the `WebSiteController.java` file directly from your IDE.

**Application URL**: http://localhost:8081

> **Note**: The application runs on port 8081 (configured in `application.properties`)

## 🔗 API Endpoints

### 1. Status Endpoint
- **URL**: `GET /status`
- **Description**: Returns server status with timestamp
- **Response Format**: JSON
- **Example Response**:
  ```json
  {
    "status": "Greetings from Spring Boot. 2025-06-26, 11:30:45.123. The server is Running!"
  }
  ```

### 2. Hello Endpoint (GET)
- **URL**: `GET /hello`
- **Parameters**: 
  - `name` (optional): Name to greet (default: "World")
- **Example**: `GET /hello?name=Catalina`
- **Response**: `Hello Catalina!`

### 3. Hello Endpoint (POST)
- **URL**: `POST /hello`
- **Parameters**: 
  - `name` (form data): Name to greet (default: "World")
- **Response**: `Hello Catalina! (via POST)`

## 📝 Form Examples

The application provides two different form implementation approaches:

### Exercise 1: Traditional Form Submission
- **Method**: POST with page reload
- **Behavior**: Submits form data and reloads the entire page
- **Use Case**: Traditional web form handling
- **Implementation**: Standard HTML form with `action="/hello"` and `method="POST"`

### Exercise 2: AJAX Form Submission
- **Method**: POST without page reload
- **Behavior**: Submits form data asynchronously and updates page content
- **Use Case**: Modern single-page application behavior
- **Implementation**: JavaScript fetch API with FormData
- **Features**:
  - Real-time response display
  - Error handling
  - Enter key support
  - Visual feedback

## 🛠️ Technologies Used

### Backend
- **Spring Boot 2.3.1**: Main framework
- **Spring Web**: Web MVC and REST capabilities
- **Maven**: Dependency management and build tool
- **Java 8**: Programming language

### Frontend
- **HTML5**: Markup structure
- **CSS3**: Styling and responsive design
- **JavaScript (ES6)**: Interactive functionality
- **Fetch API**: AJAX requests

### Testing
- **JUnit 4.11**: Unit testing framework

## ⚙️ Configuration

### Application Properties
```properties
# Server configuration
server.port=8081
```

### Maven Dependencies
```xml
<!-- Spring Boot Starter Web -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
    <version>2.3.1.RELEASE</version>
</dependency>

<!-- JUnit for testing -->
<dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.11</version>
    <scope>test</scope>
</dependency>
```

## 🐛 Troubleshooting

### Common Issues

1. **"No plugin found for prefix 'spring-boot'"**
   - **Solution**: Ensure the Spring Boot Maven plugin is properly configured in `pom.xml`
   - **Check**: Verify the plugin section includes `spring-boot-maven-plugin`

2. **Port 8081 already in use**
   - **Solution**: Change the port in `application.properties` or stop the conflicting service
   - **Alternative**: Use `server.port=8082` or any available port

3. **Application doesn't start**
   - **Check**: Ensure Java 8+ is installed and configured
   - **Verify**: Maven dependencies are properly downloaded
   - **Run**: `mvn clean install` to refresh dependencies

4. **Forms not working**
   - **Verify**: Application is running on the correct port (8081)
   - **Check**: Browser console for JavaScript errors
   - **Ensure**: Network connectivity to the backend

### Debug Commands

```bash
# Check if application is running
curl http://localhost:8081/status

# Test GET endpoint
curl "http://localhost:8081/hello?name=Test"

# Test POST endpoint
curl -X POST -d "name=Test" http://localhost:8081/hello
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📚 Learning Objectives

This project demonstrates:
- Spring Boot application structure and configuration
- RESTful web service development
- HTTP method handling (GET/POST)
- Form data processing
- Static content serving
- AJAX implementation
- Error handling and user feedback
- Modern web development practices

---

**Happy Coding!** 🚀

For questions or issues, please refer to the troubleshooting section or create an issue in the repository.