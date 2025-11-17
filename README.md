# HR App Backend

This project provides a Java backend library for an HR Swing application. It includes a Data Access Object (DAO) for performing CRUD operations on an Oracle HR database, along with the necessary data models and database connection utilities.

## Prerequisites

- Java 8 or higher
- Apache Maven
- Oracle HR Database

## Installation

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/hr-app.git
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd hr-app
    ```
3.  **Build the project:**
    ```bash
    mvn package
    ```
    This will compile the source code, run any tests, and package the application into a JAR file in the `target/` directory.

## Configuration

The database connection is configured in the `src/main/resources/database.properties` file. You will need to update this file with your Oracle HR database credentials.

```properties
db.driver=oracle.jdbc.driver.OracleDriver
db.url=jdbc:oracle:thin:@hostname:port:sid
db.username=your_username
db.password=your_password
```

## Usage

### As a Library

You can include the generated JAR file (`hr-app-1.0-SNAPSHOT.jar`) in your Swing application's classpath. You can then use the `EmployeeDAO` class to interact with the database.

```java
import com.example.hr.dao.EmployeeDAO;
import com.example.hr.model.Employee;

public class Main {
    public static void main(String[] args) {
        EmployeeDAO employeeDAO = new EmployeeDAO();

        // Get all employees
        List<Employee> employees = employeeDAO.getAllEmployees();

        // Get an employee by ID
        Employee employee = employeeDAO.getEmployeeById(100);

        // ...
    }
}
```

### Running the Test Script

The `CrudTest` class provides a simple command-line interface to test the CRUD operations.

1.  **Make sure you have configured the `database.properties` file.**
2.  **Run the `CrudTest` class:**
    ```bash
    java -cp target/hr-app-1.0-SNAPSHOT.jar com.example.hr.CrudTest
    ```

## API Documentation

The API documentation (Javadoc) is located in the `target/site/apidocs` directory. You can open the `index.html` file in your browser to view the documentation.
