# 🚀 ABSENTA - Sistem Absensi SMKN 13 Bandung

Sistem absensi modern dengan fitur validasi siswa-guru real-time untuk SMKN 13 Bandung.

## ✨ Fitur Utama

- **Student-Teacher Validation System** - Validasi kehadiran guru oleh siswa perwakilan
- **Real-time Attendance Tracking** - Pelacakan kehadiran real-time
- **Excel Export Reports** - Laporan dalam format Excel profesional
- **Mobile-First Interface** - Antarmuka yang dioptimalkan untuk mobile
- **JWT Authentication** - Sistem autentikasi yang aman
- **MySQL Database** - Database yang robust dan scalable

## 🏗️ Arsitektur

- **Backend**: Node.js + Express.js dengan TypeScript
- **Database**: MySQL (Railway)
- **Authentication**: JWT (JSON Web Tokens)
- **Real-time**: Socket.io (untuk fitur real-time)
- **Excel Export**: ExcelJS untuk laporan Excel

## 🚀 Cara Menjalankan Server

### Development Mode

```bash
npm install
npm run dev
```

### Production Mode

```bash
npm install
npm start
```

## 📋 Endpoint yang Tersedia

### Public Endpoints (Tidak Memerlukan Autentikasi)

- `GET /health` - Health check server
- `GET /api/health` - Status kesehatan detail
- `GET /status` - Status server
- `GET /api/info` - Informasi server
- `GET /api/db-test` - Test koneksi database

### Authentication Endpoints

- `POST /api/login` - Login user
- `POST /api/logout` - Logout user
- `GET /api/verify` - Verifikasi JWT token

### Protected Endpoints (Memerlukan JWT Token)

- `GET /api/dashboard/*` - Dashboard dan statistik
- `GET /api/admin/*` - Endpoint admin
- `GET /api/guru/*` - Endpoint guru
- `GET /api/siswa/*` - Endpoint siswa

## 🔐 Login Default

### Admin

- Username: `admin`
- Password: `admin123`

### Guru

- Username: `guru_matematika`
- Password: `guru123`

### Siswa Perwakilan

- Username: `perwakilan_x_ipa1`
- Password: `siswa123`

## 🗄️ Database Schema

Database menggunakan schema `db_hoyokelas` dengan tabel utama:

- `users` - Tabel user untuk autentikasi
- `guru` - Data guru
- `siswa_perwakilan` - Data siswa perwakilan
- `kelas` - Data kelas
- `mapel` - Data mata pelajaran
- `jadwal` - Jadwal pelajaran
- `absensi_guru` - Absensi guru
- `absensi_siswa` - Absensi siswa

## 🌐 Konfigurasi Production

Server dapat dikonfigurasi untuk production dengan environment variables:

```bash
NODE_ENV=production
PORT=8080
MYSQLHOST=yamanote.proxy.rlwy.net
MYSQLUSER=root
MYSQLPASSWORD=your_password
MYSQLDATABASE=railway
MYSQLPORT=23022
JWT_SECRET=your_jwt_secret
CORS_ORIGIN=*
```

## 📊 Excel Export Templates

Sistem mendukung 4 template Excel untuk SMKN 13 Bandung:

1. **PERSENTASE KETIDAKHADIRAN PESERTA DIDIK** - Multi-sheet per grade
2. **PRESENSI SISWA (Master Data)** - Data master siswa
3. **REKAP KETIDAKHADIRAN GURU** - Rekap kehadiran guru
4. **REKAP ABSENSI HARIAN** - Absensi harian

## 🔧 Troubleshooting

### Masalah "Access denied: No token provided"

Ini terjadi karena ada request yang mengakses endpoint protected tanpa JWT token. Solusi:

1. **Gunakan endpoint public** untuk health check:

   - `/health` atau `/api/health`

2. **Login terlebih dahulu** untuk mendapatkan JWT token

3. **Periksa request headers** - pastikan ada `Authorization: Bearer <token>`

### Database Connection Issues

1. Periksa kredensial database
2. Pastikan Railway MySQL service aktif
3. Gunakan endpoint `/api/db-test` untuk test koneksi

## 📱 Mobile Optimization

Sistem dioptimalkan untuk mobile dengan:

- Touch-friendly UI (minimum 44px touch targets)
- Responsive design dari 320px width
- Fast loading pada jaringan 3G
- Offline capability untuk validasi

## 🚀 Deployment

### Railway Deployment

Server sudah dikonfigurasi untuk Railway dengan:

- Auto-restart pada error
- Environment variables management
- Database connection pooling
- Health check monitoring

### Environment Variables

```bash
# Database
MYSQLHOST=yamanote.proxy.rlwy.net
MYSQLUSER=root
MYSQLPASSWORD=your_password
MYSQLDATABASE=railway
MYSQLPORT=23022

# Security
JWT_SECRET=your_secure_jwt_secret
NODE_ENV=production

# CORS
CORS_ORIGIN=*
```

## 📞 Support

Untuk bantuan teknis atau pertanyaan, silakan hubungi tim development ABSENTA.

---

**© 2025 ABSENTA - SMKN 13 Bandung. All rights reserved.**
