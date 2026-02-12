Notes & File Management System (Flask Backend)
Overview
This project is a secure, scalable backend system built with Flask, designed to handle user authentication, role-based access control, and CRUD operations for notes and file data. It includes a functional frontend built with Jinja2 templates to demonstrate seamless API integration.

## 🚀 Features
1. Authentication & Security
User Registration: Includes email verification using OTP (One-Time Password) to ensure valid user sign-ups.

Role-Based Access Control (RBAC): Distinct interfaces and permissions for User and Admin roles.

Session Management: Secure server-side session handling using flask-session.

Password Reset: Secure forgot-password flow utilizing time-sensitive tokens (stoken).

Input Validation: Regex-based sanitization for search and form inputs to prevent basic injection.

2. Core Functionality (The "Notes" Entity)
Full CRUD: Users can Create, Read, Update, and Delete personalized notes.

File Management: Upload, view, and download files directly through the dashboard.

Data Export: One-click export of notes data to Excel (.xlsx) format using flask-excel.

Real-time Search: Pattern-matching search functionality to filter notes by title or description.

3. Admin Dashboard
Secure admin login portal.

User management capabilities, including the ability to view all registered users and delete accounts.

## 🛠️ Technical Stack
Backend: Python / Flask

Database: MySQL (Relational schema for Users, Notes, and Files)

Frontend: HTML5, Jinja2 Templates, Bootstrap

Tools: mysql-connector-python, flask-session, BytesIO for binary file handling.

## 📂 Database Schema
Users Table: id, username, email, password, role.

Notes Table: nid, title, description, added_by (FK), created_at.

FileData Table: fid, filename, fdata (BLOB), added_by (FK), created_at.

## 📈 Scalability & Future Improvements
To meet high-traffic production standards, the following architectural upgrades are planned:

JWT Transition: Migrating from session-based auth to JSON Web Tokens (JWT) for stateless, scalable authentication across microservices.

Password Hashing: Implementing Bcrypt or Argon2 for industry-standard password security (moving away from plain-text storage).

API Versioning: Implementing /api/v1/ prefixes to support backward compatibility.

Containerization: Wrapping the application in Docker to ensure consistent deployment environments.

Caching: Integrating Redis to cache frequent database queries (like viewallnotes) to reduce DB load.

## ⚙️ Setup & Installation
Clone the repo: git clone <your-repo-link>

Install Dependencies: pip install -r requirements.txt

Database Setup: Import the provided .sql file into your MySQL instance.

Configure Mail: Update cmail.py with your SMTP credentials.

Run: python app.py
