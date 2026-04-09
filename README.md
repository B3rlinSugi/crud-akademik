<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a1a2e,50:16213e,100:0f3460&height=180&section=header&text=Sistem%20Data%20Akademik&fontSize=40&fontColor=e94560&animation=fadeIn&fontAlignY=38&desc=Academic%20Data%20Management%20%7C%20PHP%208%20%7C%20MySQL%20%7C%20RBAC&descAlignY=55&descColor=a8b2d8" />

[![PHP](https://img.shields.io/badge/PHP-8.0+-777BB4?style=for-the-badge&logo=php&logoColor=white)](https://php.net)
[![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://mysql.com)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com)
[![Live Demo](https://img.shields.io/badge/Live_Demo-InfinityFree-4e73df?style=for-the-badge&logo=vercel&logoColor=white)](https://crud-akademik.42web.io)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)](https://github.com/B3rlinSugi/crud-akademik)

</div>

---

## 📌 Overview

**Sistem Data Akademik** adalah aplikasi manajemen data sekolah multi-role yang dibangun dengan pendekatan terstruktur — database relasional, Role-Based Access Control (RBAC), dan dashboard statistik real-time. Dirancang untuk memudahkan pengelolaan data siswa dan kelas oleh Admin dan Staff dengan hak akses yang berbeda.

> 💡 **Fokus Teknis:** Mendemonstrasikan kemampuan desain database relasional yang solid, implementasi RBAC yang bersih, dan pola pengembangan backend yang konsisten menggunakan PHP murni dengan PDO.

### 🏆 Angka Penting

| Metrik | Detail |
|---|---|
| **3 tabel relasional** | `users`, `kelas`, `siswa` dengan FK constraints |
| **100% PDO** | Semua query menggunakan prepared statements |
| **2 role** | Admin (kontrol penuh) vs Staff (manajemen data) |
| **Live deployed** | Tersedia online di Hosting Publik |

---

## ✨ Fitur Utama

### 🔐 Autentikasi & RBAC
- **2-tier Role-Based Access Control**: Admin dan Staff dengan hak akses yang jelas berbeda.
- Session-based authentication yang aman.
- Proteksi halaman dan fungsi berdasarkan role login.

### 👨‍G Manajemen Data Siswa & Kelas
- CRUD lengkap dengan relasi ke tabel kelas (FK constrained).
- **Integritas Data**: Menggunakan `ON DELETE RESTRICT` sehingga kelas tidak bisa dihapus jika masih ada siswa terdaftar.
- Pencarian, filter, dan pagination untuk kemudahan navigasi data.

### 📊 Dashboard & Reporting
- Grafik distribusi siswa per kelas menggunakan **Chart.js**.
- Kartu ringkasan jumlah siswa, kelas, dan akun aktif secara real-time.
- **Export PDF**: Laporan siswa yang dapat diekspor per kelas untuk kebutuhan administrasi.

---

## ⚙️ DevOps & Deployment

Proyek ini telah melalui siklus deployment untuk memastikan aksesibilitas publik:

- **Hosting**: [InfinityFree](https://infinityfree.net) / Shared Hosting.
- **Deployment Strategy**: Sinkronisasi database menggunakan skema InnoDB untuk mendukung foreign keys di lingkungan produksi.
- **Security hardening**: Arsitektur query 100% aman dengan PDO untuk memastikan perlindungan terhadap celah SQL-Injection.
- **Asset Management**: Menggunakan library CDN untuk Bootstrap dan Chart.js guna mempercepat waktu muat halaman (Page Load Time).

---

## 🚀 Cara Menjalankan Secara Lokal

### Prasyarat
- PHP 8.0+
- MySQL 8.0+
- XAMPP / Laragon

### Instalasi
1. **Clone Repository:**
   ```bash
   git clone https://github.com/B3rlinSugi/crud-akademik.git
   ```
2. **Database Setup:**
   Import file `database/db_akademik.sql` ke MySQL Anda.
3. **Konfigurasi:**
   Sesuaikan kredensial database pada file `config/database.php`.

---

## 👤 Author

<div align="center">

**Berlin Sugiyanto Hutajulu**

[![GitHub](https://img.shields.io/badge/GitHub-B3rlinSugi-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/B3rlinSugi)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-berlinsugi-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/berlinsugi)
[![Portfolio](https://img.shields.io/badge/Portfolio-berlinsugi.vercel.app-4e73df?style=for-the-badge&logo=vercel&logoColor=white)](https://berlinsugi.vercel.app)

---

Built with ☕ and PHP · Academic Engineering

</div>
