# Backend-Engineering-projects
This repository provides a curated collection of tasks, challenges, and projects designed to help upcoming backend engineers hone their skills and gain practical experience in backend development. Each task includes detailed instructions, database structures, model designs, and API endpoints to implement.


`Task 1: REST API for a Library Management System`

### Objective: 
The goal of this test is to build a RESTful API for a library management system. 
The system should manage books, authors, and users. It should also handle 
borrowing and returning books, with additional features such as role-based 
access control, search, and caching.

### Requirements: 
1. Environment: 
- The candidate is required to use Laravel for this test.
- The solution should use a relational database (e.g., MySQL, PostgreSQL, 
SQLite).

2. Entities: 
Book: 
- id: Integer, primary key 
- isbn: String, required, unique 
- published_date: Date 
- author_id: Foreign key to Author 
- status: Enum [Available, Borrowed], required 
Author: 
- id: Integer, primary key 
- name: String, required 
- bio: Text, optional 
- birthdate: Date, optional 
User: 
- id: Integer, primary key 
- name: String, required 
- email: String, required, unique 
l password: String, required 
l role: Enum [Admin, Librarian, Member], required 
BorrowRecord:
id: Integer, primary key 
- user_id: Foreign key to User 
- book_id: Foreign key to Book 
- borrowed_at: DateTime, required 
- due_at: DateTime, required 
- returned_at: DateTime, optional

### API Endpoints: 
Books: 
- GET /books: Retrieve a list of all books. 
- GET /books/{id}: Retrieve details of a specific book by ID. 
- POST /books: Create a new book (Admin/Librarian only). 
- PUT /books/{id}: Update an existing book by ID (Admin/Librarian only). 
- DELETE /books/{id}: Delete a book by ID (Admin only). 
- POST /books/{id}/borrow: Borrow a book (Member only, if available). 
- POST /books/{id}/return: Return a borrowed book (Member only). 

Authors: 
l GET /authors: Retrieve a list of all authors. 
l GET /authors/{id}: Retrieve details of a specific author by ID. 
l POST /authors: Create a new author (Admin/Librarian only). 
l PUT /authors/{id}: Update an existing author by ID (Admin/Librarian only). 
l DELETE /authors/{id}: Delete an author by ID (Admin only). 

Users: 
l GET /users: Retrieve a list of all users (Admin only). 
l GET /users/{id}: Retrieve details of a specific user by ID (Admin only). 
l POST /users: Register a new user. 
l PUT /users/{id}: Update user details (Admin only or self). 
l DELETE /users/{id}: Delete a user by ID (Admin only). 
l POST /login: Authenticate a user and return a sanctum token. 
BorrowRecords: 
l GET /borrow-records: Retrieve all borrow records (Admin/Librarian only). 
l GET /borrow-records/{id}: Retrieve details of a specific borrow record by 
ID (Admin/Librarian only).
