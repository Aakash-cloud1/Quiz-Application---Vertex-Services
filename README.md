#  Quiz Application – Java Spring Boot Project

A Java – Spring Boot – Maven based Quiz Application supporting quiz creation, quiz attempts, database persistence (MySQL), authentication, and a modular MVC architecture.

This project is designed for academic & educational demonstration and showcases a full end-to-end quiz management workflow.

##  Technology Stack
- **Backend**: Java 17, Spring Boot 3.3.1
- **Database**: MySQL 8+
- **Frontend**: HTML, CSS, Thymeleaf templates
- **Build Tool**: Apache Maven

##  Key Features
- **Secure Authentication**: Role-based Login/Signup for `ADMIN` and `STUDENT`.
- **Quiz Management (Admin)**: Create, manage, edit, and delete quizzes. Add and manage questions with multiple choices.
- **Quiz Attempts (Student)**: Attempt quizzes within the designated time frame. Auto-grading and score calculation.
- **Review System**: Students can review their attempted quizzes, seeing their submitted answers and the correct answers.
- **QR Code Generation**: Generate QR codes for any public or private URLs.
- **Clean Architecture**: Follows the MVC pattern (Controllers → Services → Models).

##  Project Structure
```
Vertex MicroServices/
│── pom.xml                   # Maven dependencies and configuration
│── schema.sql                # MySQL database schema setup script
│── src/
│   ├── main/
│   │   ├── java/com/example/quizapp/
│   │   │   ├── controller/   # Web request handlers and routing
│   │   │   ├── model/        # Data structures (User, Quiz, Question, Attempt)
│   │   │   ├── service/      # Business logic (Auth, Quiz management)
│   │   │   └── qrcode/       # QR Code utility classes
│   │   └── resources/
│   │       ├── application.properties # Spring Boot & Database configuration
│   │       ├── static/       # CSS, JS, Images
│   │       └── templates/    # Thymeleaf HTML views
```

##  How to Run the Application

### Prerequisites
Ensure you have the following installed on your system:
- **Java JDK 17+** (`java -version`)
- **Apache Maven 3.6+** (`mvn -version`)
- **MySQL Server 8.x** (`mysql --version`)

### Database Setup
1. Open MySQL Workbench or MySQL CLI.
2. Run the provided `schema.sql` script to create the database and tables:
```sql
source path/to/schema.sql;
```

###  Configure Application Properties
Edit `src/main/resources/application.properties` and update it with your MySQL credentials:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/quizapp?useSSL=false&serverTimezone=UTC&allowPublicKeyRetrieval=true
spring.datasource.username=root
spring.datasource.password=your_mysql_password
```

###  Build and Run
Open a terminal in the project root directory (`Vertex MicroServices`) and run:
```powershell
mvn clean install
mvn spring-boot:run
```

###  Access the Application
Once the server starts, open your web browser and navigate to:
```
http://localhost:8080
```

##  Testing the APIs
A Postman collection `Vertex_All_Controllers.postman_collection` is included in the project root. You can import it into Postman to quickly test all the endpoints.

##  Limitations & Notes
- Only single correct answer type questions are supported.
- Correct answers are stored directly in the database without masking or encryption.
- There is currently no option to shuffle question choices dynamically.
