## 1. SELECT: Retrieves data.
Syntax:
```SQL
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
Example:
```SQL
SELECT customer_id, first_name, last_name
FROM customers
WHERE city = 'New York';
```

## 2. INSERT INTO: Adds new data.
Syntax:
```SQL
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```
Example:
```SQL
INSERT INTO customers (first_name, last_name, email)
VALUES ('John', 'Doe', 'johndoe@example.com');
```

## 3. UPDATE: Modifies existing data.
Syntax:
```SQL
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
Example:
```SQL
UPDATE customers
SET email = 'new_email@example.com'   

WHERE customer_id = 1;
```

## 4. DELETE FROM: Removes data.
Syntax:
```SQL
DELETE FROM table_name
WHERE condition;
```
Example:
```SQL
DELETE FROM customers
WHERE customer_id = 1;
```

## 5. MERGE: Synchronizes data (available from PostgreSQL 15).
Syntax:
```SQL
MERGE INTO target_table AS t
USING source_table AS s
ON t.column1 = s.column1
WHEN MATCHED THEN
    UPDATE SET t.column2 = s.column2
WHEN NOT MATCHED THEN
    INSERT (t.column1, t.column2) VALUES (s.column1, s.column2);
```
Example:
```SQL
MERGE INTO customers AS t
USING customer_updates AS s
ON t.customer_id = s.customer_id
WHEN MATCHED THEN
    UPDATE SET t.email = s.email
WHEN NOT MATCHED THEN
    INSERT (t.customer_id, t.first_name, t.last_name, t.email)
    VALUES (s.customer_id, s.first_name, s.last_name, s.email);
```
