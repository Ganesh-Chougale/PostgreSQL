## 1. ALTER DATABASE: Modifies properties of an existing database.
> Syntax: 
```sql
ALTER DATABASE database_name
    SET [CONFIG.name] = value
    [SET [CONFIG.name] = value ...];
```
> Example: 
```sql
ALTER DATABASE my_database
    SET lc_messages = 'en_US.UTF-8'
    SET wal_level = 'hot_standby';
```

## 2. ALTER TABLE: Modifies an existing table (e.g., add/drop columns, rename columns/tables).
> 1. Adding a column:
```SQL
ALTER TABLE table_name ADD COLUMN column_name data_type;
```
Example:
```SQL
ALTER TABLE customers ADD COLUMN is_active BOOLEAN;
```

> 2. Dropping a column:
```SQL
ALTER TABLE table_name DROP COLUMN column_name;
```
Example:
```SQL
ALTER TABLE customers DROP COLUMN email;
```

> 3. Renaming a table:
```SQL
ALTER TABLE table_name RENAME TO new_table_name;
```
Example:
```SQL
ALTER TABLE customers RENAME TO customer_details;
```

> 4. Renaming a column:
```SQL
ALTER TABLE table_name RENAME COLUMN old_column_name TO new_column_name;
```
Example:
```SQL
ALTER TABLE customer_details RENAME COLUMN first_name TO given_name;
```

> 5. Changing a column's data type:
```SQL
ALTER TABLE table_name ALTER COLUMN column_name TYPE new_data_type;
```
Example:
```SQL
ALTER TABLE customer_details ALTER COLUMN last_name TYPE TEXT;
```

> 6. Making a column NOT NULL:
```SQL
ALTER TABLE table_name ALTER COLUMN column_name SET NOT NULL;
```
Example:
```SQL
ALTER TABLE customer_details ALTER COLUMN given_name SET NOT NULL;
```

> 7. Adding a default value:
```SQL
ALTER TABLE table_name ALTER COLUMN column_name SET DEFAULT expression;
```
Example:
```SQL
ALTER TABLE customer_details ALTER COLUMN is_active SET DEFAULT false;
```

> 8. Removing a default value:
```SQL
ALTER TABLE table_name ALTER COLUMN column_name DROP DEFAULT;
```
Example:
```SQL
ALTER TABLE customer_details ALTER COLUMN is_active DROP DEFAULT;
```

> 9. Adding a constraint:
```SQL
ALTER TABLE table_name ADD CONSTRAINT constraint_name CHECK (condition);
```
Example:
```SQL
ALTER TABLE customer_details ADD CONSTRAINT ck_customers_active CHECK (is_active IN (true, false));
```

> 10. Dropping a constraint:
```SQL
ALTER TABLE table_name DROP CONSTRAINT constraint_name;
```
Example:
```SQL
ALTER TABLE customer_details DROP CONSTRAINT ck_customers_active;
```


## 3. ALTER VIEW: Changes properties of an existing view.
Syntax:
```SQL
ALTER VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
[WITH CHECK OPTION];
```
Example:
```SQL
ALTER VIEW active_customers AS
SELECT customer_id, first_name, last_name
FROM customers
WHERE is_active = true
WITH CHECK OPTION;
```

## 4. ALTER INDEX: Modifies an existing index.
Syntax:
```SQL
ALTER INDEX index_name
    RENAME TO new_index_name
    | USING REINDEX
    | VACUUM FULL
    | REORGANIZE;
```
Example:
```SQL
ALTER INDEX idx_customers_last_name RENAME TO idx_customer_details_last_name;
```

## 5. ALTER SCHEMA: Changes properties of an existing schema.
Syntax:
```SQL
ALTER SCHEMA schema_name
    RENAME TO new_schema_name;
```
Example:
```SQL
ALTER SCHEMA public RENAME TO my_schema;
```

## 6. ALTER SEQUENCE: Modifies an existing sequence.
Syntax:
```SQL
ALTER SEQUENCE sequence_name
    [RESTART WITH start_value]
    | [INCREMENT BY increment_value]
    | [MINVALUE min_value]
    | [MAXVALUE max_value]
    | [CACHE size];
```
Example:
```SQL
ALTER SEQUENCE customer_id_seq INCREMENT BY 2;
```

## 7. ALTER TYPE: Modifies an existing data type.
Syntax:
```SQL
ALTER TYPE type_name
    ADD ATTRIBUTE attribute_name data_type
    | DROP ATTRIBUTE attribute_name
    | RENAME ATTRIBUTE attribute_name TO new_attribute_name;
```
Example:
```SQL
ALTER TYPE contact_info ADD ATTRIBUTE address TEXT;
```

## 8. ALTER FUNCTION: Modifies an existing function.
Syntax:
```SQL
ALTER FUNCTION function_name
    RENAME TO new_function_name
    | OWNER TO new_owner;
```
Example:
```SQL
ALTER FUNCTION get_full_name RENAME TO get_customer_name;
```

## 9. ALTER MATERIALIZED VIEW: Changes properties of an existing materialized view.
ALTER MATERIALIZED VIEW
Syntax:
```SQL
ALTER MATERIALIZED VIEW materialized_view_name
    REFRESH [WITH DATA];
```
Example:
```SQL
ALTER MATERIALIZED VIEW active_customers_view REFRESH WITH DATA;
```

## 10. ALTER EXTENSION: Manages extensions.
Syntax:
```SQL
ALTER EXTENSION extension_name
    UPDATE;
```
Example:
```SQL
ALTER EXTENSION pgcrypto UPDATE;
```



