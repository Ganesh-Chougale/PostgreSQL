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
> Syntax: 
```sql
ALTER TABLE table_name
    ADD COLUMN column_name data_type [DEFAULT expression]
    | DROP COLUMN column_name [CASCADE | RESTRICT]
    | RENAME TO new_table_name
    | RENAME COLUMN old_column_name TO new_column_name
    | ALTER COLUMN column_name TYPE new_data_type
    | ALTER COLUMN column_name SET NOT NULL
    | ALTER COLUMN column_name DROP NOT NULL
    | ALTER COLUMN column_name SET DEFAULT expression
    | ALTER COLUMN column_name DROP DEFAULT
    | ADD CONSTRAINT constraint_name CHECK (condition)
    | DROP CONSTRAINT constraint_name
    | ADD PRIMARY KEY (column1, column2, ...)
    | DROP PRIMARY KEY
    | ADD UNIQUE (column1, column2, ...)
    | DROP UNIQUE (column1, column2, ...);
```
> Example: 
```sql

```

Simpler Examples:
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