
# 📚 Relational Library Management API

A powerful, lightweight RESTful API built with **Flask** and **SQLite3** that implements a relational database structure. This project showcases the clean separation of data across parent-child tables, foreign key constraint enforcement, and optimized data aggregation using advanced SQL queries.

---

## 🚀 Features

* **Relational Database Design:** Employs a strict one-to-many (`1:N`) structural relationship matching books back to their respective authors.
* **Foreign Key Constraints:** Utilizes SQLite's `PRAGMA foreign_keys = ON;` engine state to prevent orphaned data entries and maintain absolute data integrity.
* **Advanced Aggregation:** Leverages explicit `INNER JOIN` operations to compile comprehensive, unified JSON responses spanning across multiple database tables.
* **Production-Ready Validation:** Robust error handling equipped with standardized HTTP status codes (`201 Created`, `400 Bad Request`, `404 Not Found`).

---

## 🏛️ Database Architecture

Instead of organizing records into flat data lists, this engine unbundles metrics into independent structural layouts linked through matching key properties:

```text
  [author Table] (Parent)
   author_id (PK) ──┐
   author_name      │
   country          │
                    ▼ (Linked via Foreign Key Match)
             [books Table] (Child)
              book_id (PK)
              title
              price
              author_id (FK)
