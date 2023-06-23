## Create

```
Create
CREATE TABLE table_name (
column1 datatype constraints,
column2 datatype constraints,
...
);

例子：

CREATE TABLE users (
id INT NOT NULL AUTO_INCREMENT,
username VARCHAR(50) NOT NULL,
email VARCHAR(255) NOT NULL,
password VARCHAR(255) NOT NULL,
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
PRIMARY KEY (id)
);

ALTER TABLE <表名> 
[ADD <新列名> <数据类型> [完整性约束]]
[ADD <表级完整性约束>
[DROP [COLUMN] <列名> [CASCADE | RESTRICT]
[DROP CONSTRAINT <完整性约束名> [CASCADE | RESTRICT]]
[ALTER COLUMN <列名> <数据类型>]

例子：

ALTER TABLE users
ADD COLUMN first_name VARCHAR(50) AFTER username;

Drop
DROP TABLE <表名>［RESTRICT| CASCADE］;

例子：

DROP TABLE users;

Insert
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);

例子：

INSERT INTO users (username, email, password)
VALUES ('johndoe', 'johndoe@example.com', 'password123');

Delete
DELETE FROM table_name
WHERE condition;

例子：

DELETE FROM users
WHERE id = 1;

Update
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;

例子：

UPDATE users
SET email = 'johndoe_new@example.com'
WHERE id = 1;

Select
SELECT column1, column2, ...
FROM table_name
WHERE condition
ORDER BY column_name ASC/DESC;

例子：

SELECT id, username, email
FROM users
WHERE username = 'johndoe'
ORDER BY created_at DESC;

Grant/Revoke

GRANT <权限>[,<权限>]...
[ON <对象类型> <对象名>]
TO <用户>[,<用户>]...
[WITH GRANT OPTION];

REVOKE <权限>[,<权限>]...
[ON <对象类型> <对象名>]
FROM <用户>[,<用户>]...;

GRANT permission ON database_name.table_name TO 'username'@'localhost';
REVOKE permission ON database_name.table_name FROM 'username'@'localhost';

例子：

GRANT SELECT, INSERT, UPDATE ON users TO 'john'@'localhost';
REVOKE SELECT ON users FROM 'jane'@'localhost';
```

 ```
 CREATE TABLE table_name (column1 datatype constraints);
 
 Insert into tablename(v1,v2) Values (v1, v2)
 
 GRANT privilege on table TO user [with grant option]
 
 REVOKE privilege on table FROM user 
 
 UPDATE tablename SET column=value
 
 ALTER TABLE tablename [ADD <新列名> <数据类型> [完整性约束]]
 [ADD <表级完整性约束>
 [DROP [COLUMN] <列名> [CASCADE | RESTRICT]
 [DROP CONSTRAINT <完整性约束名> [CASCADE | RESTRICT]]
 [ALTER COLUMN <列名> <数据类型>]
 
 DELETE FROM table_name WHERE condition;
 ```



