# 🎓 Sistem Data Akademik — CRUD PHP + MySQL

![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?style=flat-square&logo=php&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5.3-7952B3?style=flat-square&logo=bootstrap&logoColor=white)
![PDO](https://img.shields.io/badge/PDO-Prepared_Statements-orange?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)

Aplikasi web CRUD manajemen data siswa akademik berbasis PHP & MySQL. Dilengkapi sistem autentikasi, multi-tabel dengan relasi, dashboard statistik, pencarian, pagination, dan export laporan PDF.

---

## ✨ Fitur Utama

| Fitur | Deskripsi |
|---|---|
| 🔐 **Login & Autentikasi** | Sistem login dengan bcrypt password + role-based access (Admin/Staff) |
| 🏫 **Multi-Tabel** | Relasi tabel `siswa` ↔ `kelas` dengan Foreign Key yang proper |
| 📊 **Dashboard Statistik** | Grafik jumlah siswa per kelas, total siswa, gender breakdown |
| 👨‍🎓 **Manajemen Siswa** | CRUD lengkap: tambah, lihat detail, edit, dan hapus data siswa |
| 🏛️ **Manajemen Kelas** | CRUD data kelas/jurusan yang terhubung ke data siswa |
| 🔍 **Pencarian & Filter** | Cari siswa berdasarkan nama/ID/email + filter per kelas |
| 📑 **Pagination** | Pembatasan tampilan data dengan navigasi halaman |
| 📄 **Export PDF** | Cetak laporan data siswa langsung dari browser |
| 📸 **Upload Foto** | Upload dan validasi foto profil siswa |

---

## 🛠️ Tech Stack

- **Backend** — PHP 8.x, PDO (prepared statements, no raw query)
- **Database** — MySQL 8.0 dengan Foreign Key, Index & InnoDB
- **Frontend** — Bootstrap 5.3, Font Awesome 6, Chart.js 4
- **Security** — `password_hash()` bcrypt, session management, XSS prevention

---

## 📁 Struktur Proyek

```
crud-akademik/
├── config/
│   └── database.php        # PDO connection + auth helpers
├── auth/
│   └── logout.php
├── siswa/
│   ├── index.php           # Daftar siswa + search + filter
│   ├── tambah.php          # Form tambah siswa + upload foto
│   ├── edit.php            # Form edit siswa
│   ├── detail.php          # Detail profil siswa
│   ├── hapus.php           # Hapus siswa (admin only)
│   └── export.php          # Export PDF laporan siswa
├── kelas/
│   ├── index.php           # Daftar kelas
│   ├── tambah.php
│   └── edit.php
├── assets/
│   ├── css/style.css
│   ├── js/main.js
│   └── img/
│       ├── siswa/          # Foto profil siswa
│       └── default.png
├── database/
│   └── db_akademik.sql     # Skema + data dummy
├── login.php
└── index.php               # Dashboard + statistik
```

---

## 🗄️ Skema Database

```sql
users          -- Akun login (admin/staff) dengan bcrypt password
kelas          -- Data kelas & jurusan
siswa          -- Data siswa (FK → kelas) dengan status aktif/nonaktif/lulus
```

**Relasi:**
```
kelas (1) ──── (N) siswa
```

---

## 🚀 Cara Instalasi

### Prasyarat
- PHP 8.0+
- MySQL 8.0+
- XAMPP / Laragon / web server lainnya

### Langkah Instalasi

```bash
# 1. Clone repository
git clone https://github.com/B3rlinSugi/crud-akademik.git
cd crud-akademik

# 2. Import database
mysql -u root -p < database/db_akademik.sql
```

```php
// 3. Sesuaikan konfigurasi di config/database.php
define('DB_NAME', 'db_akademik');
define('DB_USER', 'root');
define('DB_PASS', '');  // sesuaikan password MySQL kamu
```

```bash
# 4. Jalankan
php -S localhost:8080
```

---

## 🔑 Akun Default

| Role | Email | Password |
|---|---|---|
| Admin | `admin@akademik.com` | `password123` |
| Staff | `staff@akademik.com` | `password123` |

> Admin dapat menghapus data, Staff hanya bisa melihat dan mengedit.

---

## 📸 Screenshots

> *(Tambahkan screenshot dashboard, daftar siswa, form tambah siswa di sini)*

---

## 🔄 Upgrade dari Versi Sebelumnya

| Sebelum | Sesudah |
|---|---|
| Tanpa login/autentikasi ❌ | **Login + Role (Admin/Staff)** ✅ |
| MySQLi procedural | **PDO prepared statements** ✅ |
| 1 tabel (`tbl_siswa`) | **Multi-tabel dengan FK** (siswa + kelas + users) ✅ |
| Tanpa dashboard | **Dashboard + Chart.js** ✅ |
| Export belum ada | **Export Laporan PDF** ✅ |
| README milik pihak lain | **README asli developer** ✅ |

---

## 👨‍💻 Developer

**Berlin Sugi** — Fresh Graduate Teknik Informatika, Universitas Gunadarma (GPA 3.63)

[![GitHub](https://img.shields.io/badge/GitHub-B3rlinSugi-181717?style=flat-square&logo=github)](https://github.com/B3rlinSugi)

---

## 📄 Lisensi

Proyek ini menggunakan lisensi [MIT](LICENSE).
