# Alter

## Rename a Table

Change the name of a table

```sql
ALTER TABLE users
RENAME TO customers;
```

## Add a New Column

Add a new column to an existing table

```sql
ALTER TABLE users
ADD COLUMN phone_number VARCHAR(15) UNIQUE;
```

## Drop a Column

Remove a column from a table

```sql
ALTER TABLE users
DROP COLUMN phone_number;
```

## Rename a Column

Rename an existing column

```sql
ALTER TABLE users
RENAME COLUMN name TO full_name;
```

## Change a Column's Data Type

Change the data type of a column

```sql
ALTER TABLE users
ALTER COLUMN age TYPE BIGINT;
```
