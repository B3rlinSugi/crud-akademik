# 🎓 Sistem Data Akademik — CRUD Application

![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?style=flat-square&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

Academic data management system built with PHP and MySQL, featuring multi-table relational database, role-based access control, and data export functionality.

---

## Features

- Secure login with role-based access control (Admin and Staff)
- Student data management with photo upload, search, filter, and pagination
- Class management with student count per class
- Dashboard with real-time student statistics per class using Chart.js
- PDF export for student data reports filtered by class and status
- Admin and staff profile management

---

## Tech Stack

| Layer | Technology |
|---|---|
| Backend | PHP 8, PDO |
| Database | MySQL 8 (3 tables, Foreign Keys, InnoDB) |
| Frontend | Bootstrap 5, Vanilla JS, Chart.js |
| Auth | bcrypt, Role-Based Access Control, Session |
| Security | PDO Prepared Statements |

---

## Database Schema

```
users    — authentication with role (admin/staff)
kelas    — class data
siswa    — student data with FK to kelas and users
```

---

## Installation

1. Clone this repository
2. Import `database/db_akademik.sql` to MySQL
3. Configure database connection in `config/database.php`
4. Run on localhost using XAMPP or Laragon
5. Login as admin: `admin@akademik.com` / `admin123`

---

## Project Structure

```
crud-akademik/
├── config/         — database connection and helpers
├── siswa/          — student CRUD, export PDF
├── kelas/          — class management
├── auth/           — login, logout
├── assets/         — CSS, JS
└── database/       — SQL schema
```

---

## Author

**Berlin Sugiyanto** — Junior Backend Developer
- GitHub: [github.com/B3rlinSugi](https://github.com/B3rlinSugi)
- LinkedIn: [linkedin.com/in/berlinsugi](https://linkedin.com/in/berlinsugi)
- Email: berlinsugiyanto23@gmail.com
