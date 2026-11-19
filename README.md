# E-Report SKL

E-Report SKL adalah aplikasi web untuk mengirim dan memantau laporan atau pengaduan secara online. Pelapor dapat membuat laporan dan melihat perkembangannya, sementara admin meninjau laporan dan memperbarui status penanganannya.

## Fitur

- Registrasi dan login dengan akses berdasarkan peran pelapor dan admin.
- Pelapor dapat membuat, melihat, dan mengelola laporan miliknya.
- Laporan berisi judul, tanggal, uraian, serta foto opsional.
- Foto yang didukung: JPG, JPEG, PNG, atau WEBP, maksimal 2 MB.
- Admin dapat melihat laporan dan memproses statusnya secara berurutan:
  - `pending` — Menunggu
  - `proses` — Sedang Diproses
  - `selesai` — Selesai

## Teknologi

- PHP 8.3+
- Laravel 13
- Livewire 4
- SQLite (konfigurasi basis data dapat disesuaikan)
- Vite dan Tailwind CSS 4

## Persiapan

Pastikan PHP, Composer, Node.js, dan npm telah terpasang.

```powershell
git clone https://github.com/ahmadinumair/project-e-report-AhmadinUmair-260558302015.git
Set-Location project-e-report-AhmadinUmair-260558302015

composer install
Copy-Item .env.example .env
php artisan key:generate
New-Item -ItemType File -Force -Path database\database.sqlite
```

SQLite digunakan secara default. Sebelum membuat akun admin, isi `ADMIN_EMAIL` dan `ADMIN_PASSWORD` di `.env` dengan nilai milik Anda. Password admin harus memiliki minimal 12 karakter, huruf besar dan kecil, angka, serta simbol. Jangan bagikan atau commit file `.env`.

Lanjutkan persiapan aplikasi:

```powershell
php artisan migrate
php artisan db:seed
php artisan storage:link
npm install
npm run build
php artisan serve
```

Aplikasi dapat dibuka di `http://127.0.0.1:8000`. Akun admin dibuat oleh seeder berdasarkan nilai `ADMIN_EMAIL` dan `ADMIN_PASSWORD` di `.env`.

## Pengujian

Jalankan pengujian dengan:

```powershell
php artisan test
```
