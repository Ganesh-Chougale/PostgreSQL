## 1. CREATE DATABASE: Creates a new database.
> Syntax: 
```bash
CREATE DATABASE database_name;
```
> Example: 
```bash
CREATE DATABASE my_new_database;
```

## 2. CREATE TABLE: Creates a new table.
> Syntax: 
```bash
CREATE TABLE table_name (
    column1 data_type,
    column2 data_type,
    ...
    columnN data_type,
    constraints
);
```
> Example: 
```bash
CREATE TABLE customers (
    customer_id SERIAL PRIMARY KEY,
    first_name VARCHAR(50) NOT NULL,
    last_name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    address TEXT
);
```

## 3. CREATE VIEW: Creates a new view.
> Syntax: 
```bash
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
> Example: 
```bash
CREATE VIEW active_customers AS
SELECT customer_id, first_name, last_name
FROM customers
WHERE is_active = true;
```

## 4. CREATE INDEX: Creates a new index on a table.
> Syntax: 
```bash
CREATE INDEX index_name ON table_name (column_name);
```
> Example: 
```bash
CREATE INDEX idx_customers_last_name ON customers (last_name);
```

## 5. CREATE SCHEMA: Creates a new schema.
> Syntax: 
```bash
CREATE SCHEMA schema_name;
```
> Example: 
```bash
CREATE SCHEMA public;
```

## 6. CREATE SEQUENCE: Creates a new sequence.
> Syntax: 
```bash
CREATE SEQUENCE sequence_name
    START WITH start_value
    INCREMENT BY increment_value
    MINVALUE min_value
    MAXVALUE max_value
    CACHE size;
```
> Example: 
```bash
CREATE SEQUENCE customer_id_seq
    START WITH 1000
    INCREMENT BY 1
    NO MINVALUE
    NO MAXVALUE
    CACHE 10;
```

## 7. CREATE TYPE: Creates a new data type (custom types).
> Syntax: 
```bash
CREATE TYPE type_name AS (
    column1 data_type,
    column2 data_type,
    ...
);
```
> Example: 
```bash
CREATE TYPE contact_info AS (
    email VARCHAR(100),
    phone_number VARCHAR(20)
);
```

## 8. CREATE FUNCTION: Creates a new function (though often considered part of procedural language).
> Syntax: 
```bash
CREATE FUNCTION function_name(argument1 data_type, argument2 data_type, ...)
RETURNS return_type
AS
$$
    -- Function body (PL/pgSQL code)
$$
LANGUAGE plpgsql;
```
> Example: 
Function
```bash
CREATE FUNCTION get_full_name(first_name TEXT, last_name TEXT)
RETURNS TEXT
AS
$$
BEGIN
    RETURN first_name || ' ' || last_name;
END;
$$
LANGUAGE plpgsql;
```
Function Call
```bash
SELECT get_full_name('John', 'Doe');
```

## 9. CREATE TRIGGER: Creates a new trigger.
> Syntax: 
```bash
CREATE TRIGGER trigger_name
    BEFORE | AFTER | INSTEAD OF
    event_type
    ON table_name
    [FOR EACH ROW]
    WHEN (condition)
    EXECUTE PROCEDURE function_name();
```
> Example: 
```bash
CREATE TRIGGER update_last_modified
    BEFORE UPDATE
    ON customers
    FOR EACH ROW
    WHEN (OLD.first_name <> NEW.first_name OR OLD.last_name <> NEW.last_name)
    EXECUTE PROCEDURE update_last_modified_timestamp();
```

## 10. CREATE MATERIALIZED VIEW: Creates a materialized view (an extension of views with physical storage).
> Syntax: 
```bash
CREATE MATERIALIZED VIEW materialized_view_name
AS
SELECT column1, column2, ...
FROM table_name
[WITH DATA];
```
> Example: 
```bash
CREATE MATERIALIZED VIEW active_customers_view
AS
SELECT customer_id, first_name, last_name
FROM customers
WHERE is_active = true;
```

## 11. CREATE EXTENSION: Adds an extension to the database (like additional features or functionalities).
> Syntax: 
```bash
CREATE EXTENSION extension_name;
```
> Example: 
```bash
CREATE EXTENSION pgcrypto;
```