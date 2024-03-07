### SELECT Statement
- **Purpose:** Retrieves data from one or more tables in a database.
- **Example:** Get all columns from the `employees` table.
  ```sql
  SELECT * FROM employees;
  ```
- **Tip:** Use specific column names instead of `*` for efficiency, especially with large tables.

### WHERE Clause
- **Purpose:** Filters records that fulfill a specified condition.
- **Example:** Select employees in a specific department.
  ```sql
  SELECT * FROM employees WHERE department_id = 101;
  ```

### INSERT INTO Statement
- **Purpose:** Adds new rows (records) to a table.
- **Example:** Insert a new employee record.
  ```sql
  INSERT INTO employees (employee_id, first_name, last_name) VALUES (101, 'John', 'Doe');
  ```

### UPDATE Statement
- **Purpose:** Modifies existing records in a table.
- **Example:** Update an employee's email address.
  ```sql
  UPDATE employees SET email = 'john.doe@example.com' WHERE employee_id = 101;
  ```

### DELETE Statement
- **Purpose:** Removes one or more records from a table.
- **Example:** Delete a record from the `employees` table.
  ```sql
  DELETE FROM employees WHERE employee_id = 101;
  ```

### ORDER BY Clause
- **Purpose:** Sorts the result set in ascending or descending order.
- **Example:** Order employees by last name.
  ```sql
  SELECT * FROM employees ORDER BY last_name ASC;
  ```

### LIMIT Clause (or TOP, FETCH FIRST in some RDBMS)
- **Purpose:** Specifies the number of records to return from the beginning of the result set.
- **Example:** Get the top 5 employees based on salary.
  ```sql
  SELECT * FROM employees ORDER BY salary DESC LIMIT 5;
  ```

### DISTINCT Keyword
- **Purpose:** Removes duplicate values from the result set.
- **Example:** Select unique department IDs from the `employees` table.
  ```sql
  SELECT DISTINCT department_id FROM employees;
  ```

### Basic Operators
- **Types:** Arithmetic (`+`, `-`, `*`, `/`), Comparison (`=`, `!=`, `<`, `>`, `<=`, `>=`), Logical (`AND`, `OR`, `NOT`).
- **Example:** Find employees earning between certain salary ranges.
  ```sql
  SELECT * FROM employees WHERE salary BETWEEN 50000 AND 100000;
  ```

Understanding these SQL basics is crucial for querying databases effectively, manipulating data, and performing data analysis. Practice with real database systems and sample datasets can further solidify your grasp of these fundamental concepts.
