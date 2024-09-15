## 1. GRANT: Provides permissions on database objects.
Syntax:
```sql
GRANT privilege_type ON object_type object_name TO role_name;
```

### Example:
**Granting SELECT permission on a table:**
```sql
-- Grant SELECT permission on the 'employees' table to the user 'user1'
GRANT SELECT ON TABLE employees TO user1;
```
Explanation: This command allows user1 to perform SELECT queries on the employees table.

**Granting ALL privileges on a table:**
```sql
-- Grant all privileges (SELECT, INSERT, UPDATE, DELETE, etc.) on the 'employees' table to the user 'user2'
GRANT ALL PRIVILEGES ON TABLE employees TO user2;
```
Explanation: This command allows user2 to perform any operation (e.g., SELECT, INSERT, UPDATE, DELETE) on the employees table.


## 2. REVOKE: Removes permissions from database objects.
Syntax:
```sql
REVOKE privilege_type ON object_type object_name FROM role_name;
```

### **Example:
**Revoking SELECT permission on a table:**
```sql
-- Revoke SELECT permission on the 'employees' table from the user 'user1'
REVOKE SELECT ON TABLE employees FROM user1;
```
Explanation: This command removes the SELECT permission that user1 had on the employees table.

**Revoking all privileges on a table:**
```sql
-- Revoke all privileges on the 'employees' table from the user 'user2'
REVOKE ALL PRIVILEGES ON TABLE employees FROM user2;
```
Explanation: This command removes all permissions (e.g., SELECT, INSERT, UPDATE, DELETE) that user2 had on the employees table.


## 3. ALTER ROLE: Manages role attributes and memberships (can be used in conjunction with DCL operations).
Syntax:
```sql
ALTER ROLE role_name [WITH option];
```

### **Example:
**Granting a role to another role:**
```sql
-- Grant the role 'admin' to the role 'user_role'
GRANT admin TO user_role;
```
Explanation: This command makes user_role a member of the admin role, inheriting its permissions.

**Setting a password for a role:**
```sql
-- Set a password for the role 'user1'
ALTER ROLE user1 WITH PASSWORD 'securepassword';
```
Explanation: This command sets or changes the password for user1 to securepassword.

**Changing role attributes (e.g., making a role superuser):**
```sql
-- Grant superuser privileges to the role 'admin_role'
ALTER ROLE admin_role WITH SUPERUSER;
```
Explanation: This command elevates admin_role to superuser status, giving it all permissions and capabilities in the database.




