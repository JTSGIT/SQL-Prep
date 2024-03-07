### 1. SQL Basics

- **CRUD Operations:**  
  - **SELECT:** Retrieve data from one or more tables.  
    ```sql
    SELECT first_name, last_name FROM employees;
    ```
  - **INSERT:** Add new rows to a table.  
    ```sql
    INSERT INTO employees (first_name, last_name) VALUES ('John', 'Doe');
    ```
  - **UPDATE:** Modify existing data.  
    ```sql
    UPDATE employees SET email = 'john.doe@example.com' WHERE first_name = 'John' AND last_name = 'Doe';
    ```
  - **DELETE:** Remove rows from a table.  
    ```sql
    DELETE FROM employees WHERE first_name = 'John' AND last_name = 'Doe';
    ```

- **Filtering Data:**  
  Use `WHERE` to filter rows based on specific conditions.
  ```sql
  SELECT * FROM orders WHERE order_date >= '2020-01-01';
  ```

### 2. Joining Tables

- Understand how to join tables to combine related data from multiple tables based on a related column.
  ```sql
  SELECT employees.first_name, orders.order_date
  FROM employees
  JOIN orders ON employees.employee_id = orders.employee_id;
  ```

### 3. Grouping and Aggregates

- Group records and apply aggregate functions.
  ```sql
  SELECT employee_id, COUNT(*) AS total_orders
  FROM orders
  GROUP BY employee_id
  HAVING COUNT(*) > 10;
  ```

### 4. Subqueries and Common Table Expressions (CTEs)

- Subqueries can be used to nest queries within queries for complex data retrieval.
  ```sql
  SELECT employee_id, (SELECT COUNT(*) FROM orders WHERE orders.employee_id = employees.employee_id) AS total_orders
  FROM employees;
  ```
- CTEs for more readable queries.
  ```sql
  WITH total_orders AS (
    SELECT employee_id, COUNT(*) AS order_count
    FROM orders
    GROUP BY employee_id
  )
  SELECT * FROM total_orders WHERE order_count > 10;
  ```

### 5. Data Types and Functions

- Be aware of SQL functions to manipulate string, numeric, and date data.
  ```sql
  SELECT UPPER(first_name), ROUND(salary, 2)
  FROM employees
  WHERE hire_date BETWEEN '2020-01-01' AND '2020-12-31';
  ```

### 6. Indices and Performance

- Indices help speed up data retrieval but can slow down data insertion, deletion, and updates.
  ```sql
  -- Example: Creating an index on the employee_id column of the orders table
  CREATE INDEX idx_employee_id ON orders (employee_id);
  ```

### 7. Best Practices and Style

- Aliasing and clear formatting improve query readability.
  ```sql
  SELECT e.first_name AS employee_name, o.order_date
  FROM employees AS e
  JOIN orders AS o ON e.employee_id = o.employee_id;
  ```

### 8. Basic Database Design and Normalization

- Design databases to minimize redundancy and ensure data integrity.
  - Primary keys, foreign keys, and understanding normalization principles are key.
  ```sql
  -- Example: Ensuring a column is unique and not null
  ALTER TABLE employees ADD CONSTRAINT pk_employee_id PRIMARY KEY (employee_id);
  ```
