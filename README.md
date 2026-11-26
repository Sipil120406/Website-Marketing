# Jelajah Imogiri — Tropical Adventure

Website prototype responsif untuk promosi 29 destinasi wisata Imogiri dan kawasan sekitar.

## Jalankan lokal
Buka `index.html` di browser. Untuk preview lebih baik, jalankan static server:
`python -m http.server 8000`
lalu buka `http://localhost:8000`.

## Deploy ke GitHub Pages / Netlify / Vercel
Unggah folder ini ke repository GitHub. Untuk GitHub Pages: Settings → Pages → Deploy from a branch → pilih `main` dan `/root`. Untuk Netlify/Vercel, import repository dan gunakan folder root sebagai publish directory. Tidak perlu build command.

## Status fitur
- Landing page dengan hero slider otomatis.
- Katalog 29 destinasi, pencarian dan filter.
- Modal detail destinasi.
- Chatbot berbasis aturan lokal (belum AI generatif).
- Login pengunjung demo dan pemesanan simulasi berbasis localStorage.
- Dashboard admin demo (email `admin@jelajah.test`, password `admin123`) dan ekspor CSV.
- Responsif untuk desktop dan mobile.

## Penting sebelum produksi
Versi ini adalah front-end statis yang siap dipreview dan di-deploy sebagai website informasi. Login, booking, dashboard, dan chatbot masih simulasi di browser pengguna; jangan gunakan untuk transaksi sungguhan.
Untuk produksi:
1. Buat project Supabase.
2. Implementasikan Supabase Auth untuk login/registrasi.
3. Buat tabel `profiles`, `destinations`, `bookings`, `payments`; aktifkan Row Level Security (RLS).
4. Buat role admin yang ditentukan server/database, bukan dari input browser.
5. Simpan booking ke database dan validasi harga/ketersediaan di server.
6. Integrasikan payment gateway melalui backend/Edge Function. Jangan pernah menaruh secret key di HTML/JavaScript publik.
7. Hubungkan chatbot ke Gemini/OpenAI melalui backend/Edge Function. API key harus disimpan sebagai secret server-side.
8. QR e-ticket harus dibuat setelah pembayaran terverifikasi melalui webhook payment gateway.
9. Ganti foto contoh dengan foto destinasi yang memiliki izin penggunaan. Beberapa foto saat ini menggunakan gambar ilustrasi dari Unsplash.
10. Verifikasi lokasi administratif, akses, fasilitas, jam buka, harga, dan status operasional setiap destinasi dengan pengelola. Kebun Buah Mangunan, Puncak Becici, dan Grojogan Lepo berada di Dlingo (kawasan sekitar), bukan Kecamatan Imogiri.

## Catatan data
Deskripsi destinasi masih berupa pengantar umum dan bukan informasi operasional resmi. Harga tiket dan jam buka sengaja tidak direkayasa.

## Pembaruan konten wisata dan harga
- Halaman detail tiap destinasi sekarang memuat deskripsi lebih panjang, aktivitas, fasilitas, harga/tarif yang ditemukan, catatan validitas harga, dan tips berkunjung.
- Harga yang belum dapat diverifikasi ditampilkan sebagai **Belum terverifikasi**, bukan diisi dengan angka perkiraan.
- Contoh rujukan harga yang dicantumkan: Goa Cerme (dokumen standar pelayanan Pemkab Bantul 2024), Kebun Buah Mangunan (listing Atourin), Puncak Becici (informasi lama Dinas Pariwisata DIY), workshop Batik Giriloyo (Dinas Pariwisata DIY/Jadesta), serta tarif layanan Lembah Oya Kedungjati (laman Kapanewon Imogiri). Tarif-tarif ini perlu dicek kembali kepada pengelola sebelum transaksi.

## Chatbot
Chatbot saat ini menggunakan basis pengetahuan lokal untuk 29 destinasi dan dapat menjawab pertanyaan terkait nama tempat, aktivitas, tips, kategori, rekomendasi, dan harga yang tersedia. Ini merupakan **chatbot berbasis aturan/knowledge base**, belum merupakan AI generatif yang terhubung ke model bahasa. Untuk menjadikannya AI generatif sungguhan, buat backend/Edge Function dan hubungkan ke Gemini/OpenAI menggunakan API key yang disimpan sebagai secret server-side. Jangan pernah menaruh API key di file HTML publik.
