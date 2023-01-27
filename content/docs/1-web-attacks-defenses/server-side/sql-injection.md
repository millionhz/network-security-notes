---
weight: 10
title: "SQL Injection"
---

# SQL

SQL (Structured Query Language) is a programming language used for managing and manipulating relational databases. It is used to perform operations on the database, such as retrieving data, adding data, or modifying data.

- [SQL Basics - sqlitetutorial](https://www.sqlitetutorial.net/)

# SQL Injection

SQL injection is a code injection technique that exploits a security vulnerability in a website's software. The vulnerability is present when user input directly embedded into in SQL statements without sanitization.

- [SQL Injection - hacksplaining](https://www.hacksplaining.com/exercises/sql-injection)

- [SQL Injection - portswinger](https://portswigger.net/web-security/sql-injection)

## Defenses against SQL Injection

### Prepared Statements

With prepared statements, the code is first compiled, and then the parameters are replaced with values from user input. This prevents the user input from being treated as SQL code, and makes it much more difficult for an attacker to inject malicious code into the database.

```javascript
const sql = "SELECT * FROM customers WHERE address = ?";
const address = "Sideway 1633";
con.query(sql, [address], callback);
```
