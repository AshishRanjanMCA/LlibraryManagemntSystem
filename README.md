3-Tier Library Management System Using Java

We will create a real-world 3-tier Java project using:

Java
Spring Boot
HTML/CSS
MySQL
Maven

============================================================

What is 3-Tier Architecture?
----------------------------------
1. Presentation Layer  → Frontend/UI
2. Application Layer   → Business Logic
3. Database Layer      → Database


================================================

Project Features

Library Management System

Functions:

Add Books
View Books
Delete Books
Update Books
Admin Panel
MySQL Database

=============================================================
Architecture
----------------

Browser
   ↓
Controller Layer
   ↓
Service Layer
   ↓
Repository Layer
   ↓
MySQL Database



=====================================================================

STEP 1 — Install Java
------------------------
Update system:
--------------
sudo apt update && sudo apt upgrade -y

Install Java:

sudo apt install openjdk-17-jdk -y

Check:

java -version

=======================
STEP 2 — Install Maven
-------------------------
sudo apt install maven -y

Check:

mvn -version

===========================

STEP 3 — Install MySQL
------------------------
sudo apt install mysql-server -y

Start MySQL:
-----------
sudo systemctl start mysql
sudo systemctl enable mysql





==================================
STEP 4 — Create Database
--------------------------
sudo mysql

CREATE DATABASE librarydb;

Create user:
---------------
CREATE USER 'libraryuser'@'localhost' IDENTIFIED BY 'password123';

Grant permissions:
-------------------
GRANT ALL PRIVILEGES ON librarydb.* TO 'libraryuser'@'localhost';

Reload:
-----------------
FLUSH PRIVILEGES;

Exit:
-------
EXIT;

===========================================

STEP 5 — Create Spring Boot Project
----------------------------------------
Go to:
------------
Spring Initializr

Choose:

Option   	Value
--------       --------
Project 	Maven
Language	Java
Spring Boot	Latest Stable
Group	        com.library
Artifact	librarymanagement
Packaging	Jar
Java    	17

Add Dependencies
-----------------
Select:
-------
Spring Web
Spring Data JPA
MySQL Driver
Thymeleaf
Lombok

Click:
----------
Generate

==================================

STEP 6 — Extract Project
------------------------------
unzip librarymanagement.zip

Move inside:
-----------
cd librarymanagement









=====================================================================









# Library Management System

A 3-Tier Library Management System developed using Java Spring Boot, MySQL, and Thymeleaf.

---

# Project Overview

This project is a web-based Library Management System that allows users to:

* Add books
* View books
* Delete books
* Manage library records

The application follows 3-tier architecture:

1. Presentation Layer
2. Business Logic Layer
3. Database Layer

---

# Technologies Used

* Java 17
* Spring Boot
* Spring Data JPA
* Thymeleaf
* MySQL
* Maven
* HTML/CSS

---

# Architecture

Browser
↓
Controller Layer
↓
Service Layer
↓
Repository Layer
↓
MySQL Database

---

# Features

* Add new books
* Display all books
* Delete books
* MySQL database integration
* MVC architecture
* Responsive web application

---

# Project Structure

librarymanagement/

├── src/

│ ├── main/

│ │ ├── java/com/library/librarymanagement/

│ │ │ ├── controller/

│ │ │ ├── service/

│ │ │ ├── repository/

│ │ │ └── entity/

│ │

│ └── resources/

│ ├── templates/

│ └── application.properties

├── pom.xml

└── README.md

---

# Setup Instructions

## 1. Clone Repository

git clone https://github.com/YOUR_USERNAME/library-management-system.git

---

## 2. Go to Project Directory

cd library-management-system

---

## 3. Configure MySQL

Create database:

CREATE DATABASE librarydb;

Update database configuration inside:

src/main/resources/application.properties

Example:

spring.datasource.url=jdbc:mysql://localhost:3306/librarydb

spring.datasource.username=libraryuser

spring.datasource.password=password123

---

## 4. Run Application

mvn spring-boot:run

---

## 5. Open Browser

http://localhost:8080

---

# Database Configuration

spring.datasource.url=jdbc:mysql://localhost:3306/librarydb

spring.datasource.username=libraryuser

spring.datasource.password=password123

spring.jpa.hibernate.ddl-auto=update

spring.jpa.show-sql=true

---

# 3-Tier Architecture Explanation

## Presentation Layer

Handles frontend UI using Thymeleaf templates.

## Application Layer

Contains business logic using Controllers and Services.

## Database Layer

Handles database operations using JPA Repository and MySQL.

---

# Future Enhancements

* User authentication
* Role-based access
* Docker support
* Jenkins CI/CD
* Kubernetes deployment
* AWS deployment
* REST API integration

---

# Author

Ashish Ranjan

---

# License

This project is for educational and learning purposes.
