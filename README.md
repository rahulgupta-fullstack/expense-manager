# expense-manager
You need to build a simple **Expense Manager API** using **Spring Boot**.

Expense Manager API

A simple Spring Boot REST API for managing expenses. This project allows users to create, retrieve, and summarize expenses based on month and year.

Features-
--------
Add a new expense
Get all expenses
Get expense by ID
Get monthly expense summary
Input validation
Exception handling
In-memory H2 database support

Tech Stack-
---------
Java 8+
Spring Boot
Spring Web
Spring Data JPA
H2 Database
Maven
Lombok

Project Structure-
-----------------

Controller → Service → Repository → Database

src/main/java
 ├── controller
 ├── service
 ├── repository
 ├── entity
 ├── exception
 └── dto

 Expense Entity-
 --------------
 id       : Long
title    : String
amount   : Double
date     : LocalDate

API Endpoints-
-------------
 1. Add Expense -

POST /expenses

Request Body:
{
  "title": "Groceries",
  "amount": 1500,
  "date": "2026-03-30"
}

2. Get All Expenses
GET /expenses

3. Get Expense By ID
GET /expenses/{id}
Example: GET /expenses/1

4. Get Monthly Summary
GET /expenses/summary?month=3&year=2026
Response:
{
  "month": 3,
  "year": 2026,
  "totalExpense": 4500
}

Validation Rules -
----------------
-Title must not be empty
-Amount must be greater than 0
-Date must not be null

Exception Handling-
------------------

The application returns meaningful error messages for:

-Expense not found
-Invalid input data
-Validation failures
Example Response:
{
  "timestamp": "2026-03-30T10:00:00",
  "status": 400,
  "message": "Amount must be greater than 0"
}

H2 Database Configuration
--------------------------

H2 Console URL:

http://localhost:8080/h2-console

Default Credentials:
JDBC URL: jdbc:h2:mem:testdb
Username: sa
Password:

Run the Project :
----------------
Clone Repository

git clone <your-repository-url>
cd expense-manager-api

Build Project
mvn clean install

Run Application
mvn spring-boot:run

Application will start at:
-------------------------

http://localhost:8080

Sample Dependencies-
-------------------
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>


<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>


<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>

Author:-
--------

Rahul Gupta Java Full Stack Developer
