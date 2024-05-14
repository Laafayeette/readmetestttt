## Backend Orientation: Menumatic

This orientation aims to familiarize anyone interested in running and testing this project. The backend environment is written in Java 17 using the Spring Boot framework.

**IDE:** IntelliJ Ultimate Edition is recommended, but you may choose any other IDE that works best for you. The Ultimate Edition provides easy JDBC connectivity.

### Spring Boot Dependencies

- **Spring Web**
- **Spring Data JPA**
- **Spring Data REST**
- **Spring JDBC**
- **Spring Boot Test**
- **Spring Mail**
- **Jackson Databind**
- **PostgreSQL JDBC Driver**

## Step by Step Instructions for Testing and Running the Backend Locally

### Getting Started (Windows)

- **Download and Install PostgreSQL 16**: 
  [Visit the official website](https://www.postgresql.org/download/)

- **Add PostgreSQL 16 to Path Environment**:
  - Navigate to System Properties in Settings.
  - Click on Path Variables.
  - Navigate to "Path."
  - Locate the bin folder for PostgreSQL 16 on your system (e.g., `C:\Program Files\PostgreSQL\16\bin`). Add this path to your system's Path variables and press OK.

- **Creating a Database**:
  - Open the Command Line Interface (CLI) and type: 
    ```
    psql -U postgres
    ```
  - After connecting to PostgreSQL, create a new database using SQL commands.
