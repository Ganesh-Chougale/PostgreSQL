## 1. DROP DATABASE: Deletes an existing database.
Syntax:
```SQL
DROP DATABASE database_name;
```
Example:
```SQL
DROP DATABASE my_old_database;
```

## 2. DROP TABLE: Deletes an existing table.
Syntax:
```SQL
DROP TABLE table_name [CASCADE | RESTRICT];
```
Example:
```SQL
DROP TABLE customers CASCADE;
```

## 3. DROP VIEW: Deletes an existing view.
Syntax:
```SQL
DROP VIEW view_name;
```
Example:
```SQL
DROP VIEW active_customers;
```

## 4. DROP INDEX: Deletes an existing index.
Syntax:
```SQL
DROP INDEX index_name;
```
Example:
```SQL
DROP INDEX idx_customers_last_name;
```

## 5. DROP SCHEMA: Deletes an existing schema.
Syntax:
```SQL
DROP SCHEMA schema_name [CASCADE | RESTRICT];
```
Example:
```SQL
DROP SCHEMA my_schema CASCADE;
```

## 6. DROP SEQUENCE: Deletes an existing sequence.
Syntax:
```SQL
DROP SEQUENCE sequence_name;
```
Example:
```SQL
DROP SEQUENCE customer_id_seq;
```

## 7. DROP TYPE: Deletes an existing data type.
Syntax:
```SQL
DROP TYPE type_name [CASCADE | RESTRICT];
```
Example:
```SQL
DROP TYPE contact_info CASCADE;
```

## 8. DROP FUNCTION: Deletes an existing function.
Syntax:
```SQL
DROP FUNCTION function_name;
```
Example:
```SQL
DROP FUNCTION get_full_name;
```

## 9. DROP TRIGGER: Deletes an existing trigger.
Syntax:
```SQL
DROP TRIGGER trigger_name ON table_name;
```
Example:
```SQL
DROP TRIGGER update_last_modified ON customers;
```

## 10. DROP MATERIALIZED VIEW: Deletes an existing materialized view.
Syntax:
```SQL
DROP MATERIALIZED VIEW materialized_view_name;
```
Example:
```SQL
DROP MATERIALIZED VIEW active_customers_view;
```

## 11. DROP EXTENSION: Removes an extension from the database.
Syntax:
```SQL
DROP EXTENSION extension_name;
```
Example:
```SQL
DROP EXTENSION pgcrypto;
```






