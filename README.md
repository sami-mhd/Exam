# Database and Cache Services with Docker Compose
 This project sets up two essential services, a PostgreSQL database and a Redis cache, using Docker Compose. The setup is designed to facilitate easy management of both services, providing clear separation and configuration through environment variables.

## Services Overview
### Database Service (PostgreSQL)
The PostgreSQL service is the primary database, storing and managing application data. It runs on port 5432 and utilizes environment variables to securely manage credentials and database configuration.

### Cache Service (Redis)
The Redis service acts as a caching layer, storing data in memory for faster access, which can improve the performance of applications that frequently access the same data. It operates on port 6379 and can communicate with the PostgreSQL service within the same network.

### Running the Services with Docker Compose
To start both services, ensure Docker and Docker Compose are installed, then follow these steps:

    Clone the repository.

Create a .env file in the project root directory (details provided below).

Run the following command to start the services:

    docker-compose up -d
    
To stop the services, use:

    docker-compose down

## Git Branching Workflow

This project uses a simple Git branching workflow with descriptive branch naming conventions:

### Main Branch:
     main containing the code.

### Develop Branch
    maintaining the changes from feature branches

### Feature Branches:  
+ feature/database-service. for database service
+ feature/cache-service for cache service

### Environment Variable Management

Environment variables are used to configure sensitive information like database credentials securely. These variables are stored in a .env file, which is referenced by docker-compose.yml to configure the PostgreSQL service.

**.env File**

The .env file contains:

    POSTGRES_USER=myuser
    POSTGRES_PASSWORD=mypassword
    POSTGRES_DB=mydatabase

Note: The .env file is added to .gitignore to prevent sensitive information from being accidentally committed to version control.

## Files Overview
    docker-compose.yml: Defines and configures the PostgreSQL and Redis services.
    .env: Stores environment variables for secure configuration. Ensure this file is created before running Docker Compose.
    .gitignore: Includes .env to protect sensitive information.
    