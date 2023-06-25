# Structured query language

> this is mostly applied for mysql

cheatsheet

```sql
SELECT id,age FROM customers
INSERT INTO customers (id,age) VALUES (2,24)
UPDATE customers SET id = 2, age = 24
DELETE FROM customers

-- use with SELECT, UPDATE, DELETE
WHERE id = 4 AND age = 2
      id = 4 OR age >= 2
      NOT state = 'verified'
      balance BETWEEN 30 AND 50
      email LIKE '%gmail.%'
      country IN ('US','ID')
      city NOT NULL

ORDER BY age DESC
LIMIT 100
GROUP BY city
HAVING balance BETWEEN 30 AND 50


CREATE TABLE persons (
    id int,
    address varchar(255)
)

ALTER TABLE Customers
  ADD Email varchar(255)
  DROP COLUMN Email
  RENAME COLUMN id to personid
  MODIFY COLUMN column_name datatype;
  
-- constraint is used when creating a new column
id int
  NOT NULL 
  UNIQUE(id)
  PRIMARY KEY(id)
  FOREIGN KEY (personid) REFERENCES Persons(id)
  CHECK (Age>=18)
  DEFAULT 'default'
  CREATE INDEX
  AUTO_INCREMENT
  -- name constraint
  CONSTRAINT ctname UNIQUE(id)
  -- for modifying constraint use alter table



WHERE EXISTS
(SELECT city FROM customer WHERE age > 17)

SELECT DISTINCT staff FROM customers


-- alias
SELECT id AS customer_id FROM customers AS customer_table
SELECT name, CONCAT(address,', ',City,', ',Country) AS Address
-- return 2 fields: customer and address with its values combined


SELECT o.OrderID, c.CustomerName, o.OrderDate FROM Orders o
INNER JOIN Customers c ON o.id = c.id
RIGHT JOIN Customers c ON o.id = c.id
LEFT JOIN Customers c ON o.id = c.id
FULL JOIN Customers c ON o.id = c.id


-- functions, will return one record
-- use after SELECT before FROM
MIN(balance)
MAX(age)
COUNT(), AVG(), SUM()

-- Date data types
DATE      -- format YYYY-MM-DD
DATETIME  -- format: YYYY-MM-DD HH:MI:SS
TIMESTAMP -- format: YYYY-MM-DD HH:MI:SS
YEAR      -- format YYYY or YY

-- like wildcards
LIKE  '%as%'    -- any characters
      '_am_'    -- any one character
      '[abc]%'  -- specified character
      '[!abc]%' -- not specified character
```
