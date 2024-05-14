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

### Getting Started (macOS)

- **Download and Install PostgreSQL 16**: 
  [Visit the official website](https://www.postgresql.org/download/)

- **Add PostgreSQL 16 to Path Environment**:
  - Open Terminal.
  - Edit your shell profile file (e.g., `.bash_profile`, `.zshrc`, or `.bashrc`) using a text editor like nano or vim. For example:
    ```
    nano ~/.bash_profile
    ```
  - Add the following line to the end of the file, replacing `<installation_path>` with the actual path where PostgreSQL is installed (e.g., `/Library/PostgreSQL/16/bin`):
    ```
    export PATH=$PATH:<installation_path>
    ```
  - Save and close the file.
  - Restart Terminal or run `source ~/.bash_profile` for the changes to take effect.



### Getting Started (cont.)
- **Creating a Database**:
  - Open the Command Line Interface (CLI) and type: 
    ```
    psql -U postgres
    ```
  - You may be asked to enter password. If you don't have one yet, press enter to skip.
  - After connecting to PostgreSQL, create a new database using the following SQL command.
    ```
    CREATE DATABASE database_name;
    ```
  - Connect to the newly created database.
    ```
    \c database_name
    ```
  - Now we must import the db_import.sql file which will generate the database schema for Menumatic.
  - Download the db_import.sql file from the [Menumatic Backend Github Page](https://github.com/team-havstrut-2024/menumatic-backend)
  - Locate to the directory it was downloaded onto (e.g., `C:\Dokument\Menumatic\Backend`) and copy path.
  - Now we must cd into the path in the CLI, and as such we must disconnect from the database:
    ```
    CTRL + c
    ```
  - Enter the path for the db_import.sql file (example): 
    ```
    cd C:\Dokument\Menumatic\Backend
    ```
  - Now connect back into the database using the step shown above.
  - Once connected we import the database schema dump:
    ```
    \i db_import.sql
    ```
  - To verify everything looks good you can enter ``` \dt ``` and the tables ought to be displayed.

- **Cloning the Github Repository**:
  - Before we can connect the database to our codebase, we must first clone our backend environment's repository.
  - Clone the repository from [Menumatic Backend Github Page](https://github.com/team-havstrut-2024/menumatic-backend) into any directory of your choice.

- **Creating a Maven Project (Instructions are for Intellij)**:
  - Run Intellij Ultimate Edition (any edition works fine).
  - Select ``` New project from existing sources ```
  - Choose the folder in which you cloned the repository and press OK.
  - Choose Maven and press OK.
  - Verify that the pom.xml file matches the one on Github.

- **Connecting to the database via Spring JDBC**
  - Now we are ready to connect our codebase to the database.
  - Navigate to the "resources" folder and open the ``` application.properties ```.
  - Modify the `spring.datasource.url`, `spring.datasource.username`, and `spring.datasource.password` to match your PostgreSQL credentials and database name.

  - Looking at the:
    ```
    spring.datasource.url=jdbc:postgresql://localhost:5432/menumatic
    ```
    The ``` /menumatic ``` represents the name of your database. Meaning, replace "menumatic" with whatever you named your database.
  - Modify the values below to match your PostgreSQL credentials:
    ```
    spring.datasource.username=<your username, usually is "postgres">
    spring.datasource.password=<password, empty if you have none>
    ```
  - Now we are ready to run the application.
  - Run the application by running `MenumaticApplication`.

  - Alternatively, you can connect to the database via IntelliJ:
    - On the right side of IntelliJ, press on the database logo.
    - Click on `New` -> `Data Source` -> `PostgreSQL`.
    - Enter your username and password.
    - `Database: <Name of your database>`.
    - Test the connection, apply, and then OK.


