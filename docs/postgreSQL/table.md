# Table

## Create a Database

```sql
CREATE DATABASE example_db;
```

## Drop the Database

```sql
DROP DATABASE example_db;
```

## Create a Table

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(150) UNIQUE NOT NULL,
    age INT CHECK (age >= 0),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Insert Data into the Table

```sql
INSERT INTO users (name, age, email)
VALUES
('Alice', 25, 'alice@example.com'),
('Bob', 30, 'bob@example.com');
```

```sql
INSERT INTO users VALUES
('Alice', 'alice@example.com', 25),
('Bob', 'bob@example.com', 30);
```

## Query the Data

```sql
SELECT * FROM users;
SELECT name FROM users;
```

## Update Data

```sql
UPDATE users
SET age = 26
WHERE name = 'Alice';
```

## Delete Data

```sql
DELETE FROM users
WHERE name = 'Bob';
```

## Drop the Table

```sql
DROP TABLE users;
```
