# Spring AI RAG DB Example

This project demonstrates a Spring Boot application integrating AI-powered Retrieval-Augmented Generation (RAG) with a database backend.

## Prerequisites
- Java 17 or higher
- Gradle
- MySQL Server
- [Ollama](https://ollama.com/) (for local LLM inference)

## Setup Instructions

### 1. Clone the Repository
```
git clone <repo-url>
cd spring-ai-rag-db
```

### 2. Configure MySQL
- Create a MySQL database and user as specified in `src/main/resources/application.properties`:

```
spring.datasource.url=jdbc:mysql://localhost:3306/<your_db_name>
spring.datasource.username=<your_db_user>
spring.datasource.password=<your_db_password>
```
- Update the above values in `application.properties` if needed.
- Run the SQL script in `src/main/resources/mysql.txt` to set up the required tables.

### 3. Configure Ollama
- Install Ollama from [Ollama Downloads](https://ollama.com/download).
- Start Ollama locally:
```
ollama serve
```
- Ensure the following properties are set in `application.properties`:
```
spring.ai.ollama.base-url=http://localhost:11434
spring.ai.ollama.model=<your_model_name>
```
- Download the required model using:
```
ollama pull <your_model_name>
```

### 4. Build the Project
```
./gradlew build
```

### 5. Run the Application
```
./gradlew bootRun
```

The application will start on the default port (8080). You can access the REST endpoints as defined in the controllers.

## Additional Notes
- All configuration is managed via `src/main/resources/application.properties`.
- For troubleshooting, check the logs and ensure MySQL and Ollama are running and accessible.

## License
MIT

