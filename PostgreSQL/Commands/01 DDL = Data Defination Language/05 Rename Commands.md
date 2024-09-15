## 1. RENAME TABLE: Renames an existing table.
Syntax:
```SQL
ALTER TABLE table_name RENAME TO new_table_name;
```
Example:
```SQL
ALTER TABLE customers RENAME TO customer_details;
```

## 2. RENAME COLUMN: Renames a column in a table.
Syntax:
```SQL
ALTER TABLE table_name RENAME COLUMN old_column_name TO new_column_name;
```
Example:
```SQL
ALTER TABLE customer_details RENAME COLUMN first_name TO given_name;
```

## 3. RENAME VIEW: Renames an existing view.
Syntax:
```SQL
ALTER VIEW view_name RENAME TO new_view_name;
```
Example:
```SQL
ALTER VIEW active_customers RENAME TO active_customer_details;
```

## 4. RENAME SEQUENCE: Renames an existing sequence.
Syntax:
```SQL
ALTER SEQUENCE sequence_name RENAME TO new_sequence_name;
```
Example:
```SQL
ALTER SEQUENCE customer_id_seq RENAME TO customer_details_id_seq;
```

## 5. RENAME SCHEMA: Renames an existing schema.
Syntax:
```SQL
ALTER SCHEMA schema_name RENAME TO new_schema_name;
```
Example:
```SQL
ALTER SCHEMA public RENAME TO my_schema;
```

