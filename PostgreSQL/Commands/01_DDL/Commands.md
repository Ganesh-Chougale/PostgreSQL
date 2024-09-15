# Data Definition Language

## 1. Create Table
<details>
  <summary>Command to Create Table</summary>
  ```bash
  CREATE TABLE table_name (
    column_name data_type [constraints]
    );
  ```
> Example
  ```sql
    CREATE TABLE customers (
        customer_id SERIAL PRIMARY KEY,
        first_name VARCHAR(50) NOT NULL,
        last_name VARCHAR(50) NOT NULL,
        email VARCHAR(100) UNIQUE
    );
  ```
</details>

## 2. 
<details>
  <summary>Command to </summary>
  ```bash

  ```
</details>