# 🎓 Sistem Data Akademik — Academic Data Management System

A multi-role academic data management system with a relational database, role-based access control (RBAC), and statistical dashboard—built with PHP 8 and MySQL. Designed with a focus on data integrity and standardized backend patterns.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-crud--akademik.42web.io-4e73df?style=for-the-badge&logo=infinity)](https://crud-akademik.42web.io)
[![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4?style=for-the-badge&logo=php)](https://php.net)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql)](https://mysql.com)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=for-the-badge&logo=bootstrap)](https://getbootstrap.com)

---

## 📋 Table of Contents

- [Live Demo](#-live-demo)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Database Schema](#-database-schema)
- [Project Structure](#-project-structure)
- [Installation (Local)](#-installation-local)
- [Deployment (InfinityFree)](#-deployment-infinityfree)
- [Default Credentials](#-default-credentials)
- [Author](#-author)

---

## 🌐 Live Demo

**[https://crud-akademik.42web.io](https://crud-akademik.42web.io)**

> *Note: If the link shows a "403 Forbidden" or "Account Verification" page, it means the hosting provider (InfinityFree) is still propagating the new account. It should be live within 24 hours.*

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔐 **RBAC Security** | Two-tier access: **Admin** (System controls) and **Staff** (Data management) |
| 📊 **Analytics Dashboard** | Real-time charts showing student distribution per class |
| 👨‍🎓 **Student Management** | Full CRUD with automatic ID generation and class relations |
| 🏫 **Class Management** | CRUD for academic classes/departments linked to students |
| 🔍 **Advanced Filtering** | Integrated search and class-based filtering across all listings |
| 📄 **PDF Reporting** | Month and class-filtered PDF generation for academic records |
| 🛡️ **PDO Protection** | 100% prepared statements to eliminate SQL Injection risks |

---

## 🛠 Tech Stack

| Technology | Role |
|---|---|
| **PHP 8.0+** | Procedural logic with PDO DB access |
| **MySQL 8** | Relational data with Foreign Key constraints |
| **Bootstrap 5** | Clean, responsive UI design |
| **Chart.js 4** | Academic distribution visualization |
| **TCPDF / FPDF** | Server-side PDF generation |
| **InfinityFree** | Cloud deployment for academic projects |

---

## 🗄 Database Schema

### Tables

```
users          — System accounts with 'admin' or 'staff' roles
kelas          — Master table for departments/classes
siswa          — Core student records with class relationship (FK constrained)
```

### Relationships

```
kelas (1) ──< siswa (N)
```

> **Data Integrity:** Uses `ON DELETE RESTRICT` on class-to-student relations to prevent orphaned student records.

---

## 📁 Project Structure

```
crud-akademik/
├── assets/             # Shared CSS, JS, and vendor libraries
├── auth/               # Login, logout, and profile management
├── config/
│   └── database.php    # Database connection + helper functions
├── database/
│   └── db_akademik.sql # Database schema + seed data
├── kelas/              # Class/Department management modules
├── siswa/              # Student management (CRUD) modules
├── index.php           # Main dashboard with statistics
├── login.php           # Entry point
└── .htaccess           # URL routing and security config
```

---

## 🚀 Installation (Local)

### Prerequisites
- PHP 8.0+
- MySQL 8.0+
- Local server (XAMPP / WAMP / Laragon)

### Steps

```bash
# 1. Clone the repository
git clone https://github.com/B3rlinSugi/crud-akademik.git
cd crud-akademik

# 2. Create database
mysql -u root -p -e "CREATE DATABASE db_akademik;"

# 3. Import schema
mysql -u root -p db_akademik < database/db_akademik.sql
```

Update `config/database.php` with your local credentials.

---

## 🔑 Default Credentials

| Role | Email | Password |
|---|---|---|
| **Admin** | `admin@akademik.com` | `admin123` |
| **Staff** | `staff@akademik.com` | `admin123` |

---

## 👨‍💻 Author

**Berlin Sugiyanto Hutajulu**

[![GitHub](https://img.shields.io/badge/GitHub-B3rlinSugi-181717?style=flat&logo=github)](https://github.com/B3rlinSugi)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-berlinsugi-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/berlinsugi)
[![Portfolio](https://img.shields.io/badge/Portfolio-berlinsugi.vercel.app-4e73df?style=flat&logo=vercel)](https://berlinsugi.vercel.app)

---

<p align="center">Academic Data Management System · Built for Faculty Operations</p>
