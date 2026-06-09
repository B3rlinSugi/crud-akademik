<div align="center">
  <br />
  <h1>🎓 CRUD Akademik</h1>
  <p>
    <strong>Academic Data Management System with Strict Database Integrity</strong>
  </p>
  <p>
    <img src="https://img.shields.io/badge/PHP_8-777BB4?style=for-the-badge&logo=php&logoColor=white" alt="PHP 8" />
    <img src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white" alt="MySQL" />
    <img src="https://img.shields.io/badge/Bootstrap_5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap" />
    <img src="https://img.shields.io/badge/PDO_Security-000000?style=for-the-badge&logo=shield&logoColor=white" alt="PDO" />
  </p>
  <p>
    <a href="https://crud-akademik.vercel.app/" target="_blank">View Live Demo</a>
  </p>
</div>

---

## 📌 Overview

**CRUD Akademik** is a native PHP-based web application built to manage academic data efficiently. The primary focus of this project is demonstrating **Strict Database Integrity** and **Application Security** using raw PHP Data Objects (PDO). 

Instead of relying on ORMs to handle relationships, this system utilizes pure SQL queries with `ON DELETE RESTRICT` constraints to prevent orphaned records, ensuring that class data cannot be deleted if students are still enrolled.

## ✨ Key Features

- **Strict Relational Integrity**: Implements `ON DELETE RESTRICT` foreign keys. If an administrator attempts to delete a class (`Kelas`) that contains active students, the database actively rejects the query, preventing data corruption.
- **Role-Based Access Control (RBAC)**: Distinct dashboards and permissions for `Admin` (full access) and `Staff` (view/edit limited).
- **Advanced Data Tables**: Features robust server-side data handling including pagination, multi-column search, and filtering.
- **Automated PDF Reporting**: Generates formatted PDF reports of academic records using `TCPDF/FPDF` libraries.
- **Bulletproof Security**: Prevents SQL Injection through strict implementation of PDO Prepared Statements on all queries.

---

## 🛠️ Tech Stack & Architecture

- **Backend**: Native PHP 8
- **Database**: MySQL 8.x
- **Database Extension**: PDO (PHP Data Objects)
- **Frontend Framework**: HTML5, CSS3, Bootstrap 5
- **Reporting Engine**: TCPDF / FPDF for document generation
- **Architecture**: Procedural Native combined with structured directories (`/auth`, `/kelas`, `/siswa`).

---

## 🗄️ Database Integrity Snapshot

```sql
-- Example of strict relational mapping used in this project
CREATE TABLE tb_siswa (
    id_siswa INT PRIMARY KEY AUTO_INCREMENT,
    nis VARCHAR(20) UNIQUE NOT NULL,
    nama_siswa VARCHAR(100) NOT NULL,
    id_kelas INT NOT NULL,
    CONSTRAINT fk_kelas 
        FOREIGN KEY (id_kelas) 
        REFERENCES tb_kelas(id_kelas)
        ON DELETE RESTRICT 
        ON UPDATE CASCADE
);
```

---

## 🚀 Getting Started

### Prerequisites
- **Apache Web Server** (XAMPP / Laragon)
- **PHP 8.0+**
- **MySQL Database**

### Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/B3rlinSugi/crud-akademik.git
   cd crud-akademik
   ```

2. **Database Setup:**
   - Create a new MySQL database named `db_akademik`.
   - Import the provided SQL dump located at `database/db_akademik.sql`.

3. **Configure Connection:**
   - Open `config/database.php`.
   - Update the PDO connection parameters to match your local environment.

4. **Run the Application:**
   - Ensure the project is in your web server's root directory (`htdocs` or `www`).
   - Open your browser: `http://localhost/crud-akademik`.

---

## 👨‍💻 Author

**Berlin Sugiyanto**  
Backend Developer & System Architect  
- Portfolio: [berlinsugi.vercel.app](https://berlinsugi.vercel.app/)
- LinkedIn: [linkedin.com/in/berlinsugi](https://linkedin.com/in/berlinsugi)

---

<div align="center">
  <i>"Data integrity at the database level is the first line of defense."</i>
</div>
