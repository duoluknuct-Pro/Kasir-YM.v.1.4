# YANG MULIA POS
Kasir & Manajemen Stok Batagor dan Siomay Ikan.

## 1. Supabase
1. Buat project di Supabase.
2. Buka SQL Editor.
3. Jalankan `supabase/schema.sql`.
4. Buat user pertama di Authentication > Users.
5. Masukkan UUID user tersebut ke `profiles` dan role `OWNER`.

## 2. Frontend
Edit `src/config.js`:
- SUPABASE_URL
- SUPABASE_ANON_KEY / publishable key

Jangan masukkan service_role key.

## 3. Lokal
Jalankan server statis, misalnya VS Code Live Server atau `python -m http.server 8080`.
Buka `http://localhost:8080`.

## 4. GitHub Pages
Push repository ke GitHub. Workflow `.github/workflows/deploy.yml` akan mem-publish folder project.

## 5. PWA Android
Buka URL GitHub Pages dari Chrome Android lalu pilih Install app / Add to Home Screen. HTTPS diperlukan untuk service worker di production.

## Catatan offline
MVP ini menyimpan katalog dan transaksi lokal menggunakan IndexedDB dan menyediakan antrean sinkronisasi dasar. Untuk produksi multi-kasir, tahap berikutnya wajib menambahkan idempotency, sinkronisasi sale_items + stock_movements, conflict handling, dan rekonsiliasi stok server.
