<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100:0f3460&height=180&section=header&text=Sistem%20Data%20Akademik&fontSize=40&fontColor=e94560&animation=fadeIn&fontAlignY=38&desc=Academic%20Data%20Management%20%7C%20PHP%208%20%7C%20MySQL%20%7C%20RBAC&descAlignY=55&descColor=a8b2d8" />

[![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://php.net)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://mysql.com)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-crud--akademik.42web.io-4e73df?style=for-the-badge&logo=vercel&logoColor=white)](https://crud-akademik.42web.io)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)](https://github.com/B3rlinSugi/crud-akademik)

</div>

---

## 🌐 Live Demo

> **[https://crud-akademik.42web.io](https://crud-akademik.42web.io)**

Sistem ini sudah di-deploy dan dapat diakses secara publik. Gunakan kredensial di bagian bawah untuk mencoba.

---

## 📌 Overview

**Sistem Data Akademik** adalah aplikasi manajemen data sekolah multi-role yang dibangun dengan pendekatan terstruktur — database relasional, Role-Based Access Control (RBAC), dan dashboard statistik real-time. Dirancang untuk memudahkan pengelolaan data siswa dan kelas oleh Admin dan Staff dengan hak akses yang berbeda.

> 💡 **Fokus utama:** Mendemonstrasikan kemampuan desain database relasional yang solid, implementasi RBAC yang bersih, dan pola pengembangan backend yang konsisten menggunakan PHP murni dengan PDO.

### 🏆 Angka Penting

| Metrik | Detail |
|---|---|
| **3 tabel relasional** | `users`, `kelas`, `siswa` dengan FK constraints |
| **100% PDO** | Semua query menggunakan prepared statements |
| **2 role** | Admin (kontrol penuh) vs Staff (manajemen data) |
| **Live deployed** | Tersedia online di InfinityFree hosting |

---

## ✨ Fitur Utama

### 🔐 Autentikasi & RBAC
- **2-tier Role-Based Access Control**: Admin dan Staff dengan hak akses yang jelas berbeda
- Session-based authentication yang aman
- Halaman dan fungsi terlindungi berdasarkan role

| Hak Akses | Admin | Staff |
|---|---|---|
| Kelola pengguna sistem | ✅ | ❌ |
| CRUD data siswa | ✅ | ✅ |
| CRUD data kelas | ✅ | ✅ |
| Lihat dashboard statistik | ✅ | ✅ |
| Export PDF laporan | ✅ | ✅ |

### 👨‍🎓 Manajemen Data Siswa
- CRUD lengkap dengan relasi ke tabel kelas (FK constrained)
- Pencarian dan filter berdasarkan nama dan kelas
- Pagination untuk navigasi data besar
- Generasi ID otomatis

### 🏫 Manajemen Kelas
- CRUD data kelas/jurusan
- Proteksi `ON DELETE RESTRICT` — kelas tidak bisa dihapus jika masih ada siswa terdaftar (menjaga integritas data)

### 📊 Dashboard Statistik
- Grafik distribusi siswa per kelas menggunakan **Chart.js 4**
- Kartu ringkasan jumlah siswa, kelas, dan akun aktif
- Data real-time dari database

### 📄 PDF Export
- Laporan siswa yang dapat diekspor per kelas
- Format yang sesuai untuk kebutuhan administrasi akademik

---

## 🗄️ Desain Database

### Tabel

```
┌─────────────────────────────────────────────────────────┐
│                    DATABASE SCHEMA                      │
├──────────┬──────────────────────────────────────────────┤
│ users    │ Akun sistem dengan role 'admin' atau 'staff' │
│ kelas    │ Master tabel kelas/jurusan                   │
│ siswa    │ Data siswa dengan relasi ke kelas (FK)       │
└──────────┴──────────────────────────────────────────────┘
```

### Relasi

```
kelas (1) ──────< siswa (N)
  id                kelas_id (FK)
```

> **Integritas Data:** Menggunakan `ON DELETE RESTRICT` pada relasi kelas-siswa untuk mencegah orphaned records.

---

## 🏗️ Arsitektur Sistem

```
┌─────────────────────────────────────────────┐
│               CLIENT LAYER                  │
│       Browser (HTML/CSS/Bootstrap 5)        │
└────────────────────┬────────────────────────┘
                     │ HTTP Request
┌────────────────────▼────────────────────────┐
│            APPLICATION LAYER (PHP 8)        │
│                                             │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  │
│  │   Auth   │  │  Siswa   │  │  Kelas   │  │
│  │  (RBAC)  │  │  (CRUD)  │  │  (CRUD)  │  │
│  └──────────┘  └──────────┘  └──────────┘  │
│  ┌──────────┐  ┌──────────┐                 │
│  │Dashboard │  │   PDF    │                 │
│  │(Chart.js)│  │  Export  │                 │
│  └──────────┘  └──────────┘                 │
└────────────────────┬────────────────────────┘
                     │ PDO (Prepared Statements)
┌────────────────────▼────────────────────────┐
│             DATABASE LAYER                  │
│          MySQL 8 (InnoDB, FK)               │
│       users │ kelas │ siswa                 │
└─────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

| Layer | Teknologi | Alasan |
|---|---|---|
| Language | PHP 8.0+ | Stable, widely used, native PDO |
| Database | MySQL 8 (InnoDB) | FK constraints + relational integrity |
| DB Access | PDO Prepared Statements | SQL injection prevention |
| Frontend | Bootstrap 5, HTML5, CSS3, JS | Clean responsive UI |
| Charts | Chart.js 4 | Lightweight, flexible |
| PDF | TCPDF / FPDF | Server-side PDF generation |
| Hosting | InfinityFree | Cloud deployment untuk demo |

---

## 🚀 Cara Menjalankan

### Prasyarat
- PHP 8.0+
- MySQL 8.0+
- XAMPP / WAMP / Laragon

### Instalasi Lokal

```bash
# 1. Clone repository
git clone https://github.com/B3rlinSugi/crud-akademik.git
cd crud-akademik

# 2. Buat database
mysql -u root -p -e "CREATE DATABASE db_akademik;"

# 3. Import skema
mysql -u root -p db_akademik < database/db_akademik.sql

# 4. Konfigurasi koneksi
# Edit config/database.php dengan kredensial lokal kamu

# 5. Jalankan
# Letakkan di htdocs (XAMPP) atau www (Laragon)
# Akses: http://localhost/crud-akademik
```

### Kredensial Default

| Role | Email | Password |
|---|---|---|
| **Admin** | admin@akademik.com | admin123 |
| **Staff** | staff@akademik.com | admin123 |

---

## 📁 Struktur Proyek

```
crud-akademik/
├── assets/             # CSS, JS, vendor libraries (Bootstrap, Chart.js)
├── auth/               # Login, logout, profile management
├── config/
│   └── database.php    # Koneksi DB + helper functions
├── database/
│   └── db_akademik.sql # Skema DB + seed data
├── kelas/              # Modul manajemen kelas (CRUD)
├── siswa/              # Modul manajemen siswa (CRUD)
├── composer.json       # Dependency management
├── index.php           # Dashboard utama (statistik + charts)
└── login.php           # Entry point / halaman login
```

---

## ⚙️ DevOps & Deployment

- **Hosting**: [InfinityFree](https://infinityfree.net)
- **Strategi Deployment**: Sinkronisasi file manual dengan rutinitas backup database otomatis.
- **Audit Keamanan**: Arsitektur query 100% aman dengan PDO untuk memastikan nol celah SQL-Injection.
- **Monitoring**: Terhubung ke sistem health-check Portfolio terpusat melalui probe HTTP HEAD standar.

---

## 👤 Author

<div align="center">

**Berlin Sugiyanto Hutajulu**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-berlinsugi-0077B5?style=flat-square&logo=linkedin)](https://linkedin.com/in/berlinsugi)
[![Portfolio](https://img.shields.io/badge/Portfolio-berlinsugi.vercel.app-4e73df?style=flat-square&logo=vercel)](https://berlinsugi.vercel.app)
[![Email](https://img.shields.io/badge/Email-berlinsugiyanto23%40gmail.com-D14836?style=flat-square&logo=gmail)](mailto:berlinsugiyanto23@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-B3rlinSugi-181717?style=flat-square&logo=github)](https://github.com/B3rlinSugi)

---

<div align="center">

*Academic Data Management System · Built for Faculty Operations*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f3460,50:16213e,100:1a1a2e&height=100&section=footer" />

</div>
