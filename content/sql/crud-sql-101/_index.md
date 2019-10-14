+++
title = "CRUD & SQL 101"
outputs = ["Reveal"]
+++

# CRUD & SQL 101

---

## Overview

- Intro to Databases
- Intro to CRUD
- Intro to SQL
- Installing Postgres
- How to use Postgres

---

# What's a database?

---

## Intro to Databases

> A database is an organized collection of data, generally stored and accessed electronically from a computer system. Where databases are more complex they are often developed using formal design and modeling techniques. - [Wikipedia](https://en.wikipedia.org/wiki/Database)

---

## Intro to CRUD

Create, read, update and delete for persistent storage

[Wikipedia entry for CRUD](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete)

---

## CRUD Explained

- Create (Add New)
- Read (Retrieve)
- Update (Modify)
- Delete (Destroy)

---

## Intro to SQL

Structured Query Language

---

> SQL (Structured Query Language) is a domain-specific language used in programming and designed for managing data held in a **relational database management system (RDBMS)**, or for stream processing in a relational data stream management system (RDSMS). It is particularly useful in handling structured data, i.e. data incorporating **relations** among entities and variables.

---

## Postgres SQL

https://www.postgresql.org

---

# Postgres App

https://postgresapp.com/

---

## How to use Postgres

---

### Creating a database

```sql
CREATE DATABASE [IF EXISTS] db_name;
```

---

### Drop (delete) a database

```sql
DROP DATABASE [IF EXISTS] db_name;
```

---

### Connecting to a database

```sql
\c db_name
```

---

## Creating a table

```sql
CREATE TABLE t (
  id INT PRIMARY KEY,
  name VARCHAR NOT NULL,
  price INT DEFAULT 0
);
```

[Data types](https://www.postgresql.org/docs/11/datatype.html)
