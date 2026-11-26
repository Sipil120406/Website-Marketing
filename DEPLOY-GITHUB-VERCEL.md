# Jelajah Imogiri — Panduan Deploy

## Isi folder
- `index.html` — website utama (langsung dapat di-host sebagai situs statis)
- `supabase-schema.sql` — skema awal database (opsional; tidak diperlukan untuk menampilkan website)
- `SUMBER-FOTO.md` — catatan sumber foto

## Deploy melalui GitHub dan Vercel

### 1. Unduh dan ekstrak
1. Unduh file ZIP website.
2. Ekstrak ZIP di komputer.
3. Pastikan `index.html` berada di folder utama proyek, bukan di dalam folder bertingkat tambahan.

### 2. Upload ke GitHub
1. Buka https://github.com lalu masuk atau buat akun.
2. Klik tombol **New** untuk membuat repository.
3. Beri nama, misalnya `jelajah-imogiri`.
4. Pilih **Public** atau **Private**, lalu klik **Create repository**.
5. Di halaman repository, klik **Add file → Upload files**.
6. Buka folder hasil ekstrak, pilih semua isi folder (index.html, README.md, SUMBER-FOTO.md, supabase-schema.sql), lalu seret ke area upload.
7. Isi pesan commit, misalnya `Upload website Jelajah Imogiri`, lalu klik **Commit changes**.

### 3. Deploy melalui Vercel
1. Buka https://vercel.com dan pilih **Continue with GitHub**.
2. Berikan izin akses ke repository `jelajah-imogiri`.
3. Klik **Add New → Project**.
4. Pilih repository tersebut, lalu klik **Import**.
5. Pada pengaturan proyek:
   - **Framework Preset:** Other
   - **Root Directory:** `./`
   - **Build Command:** kosongkan / None
   - **Output Directory:** `./`
   - **Install Command:** kosongkan / None
6. Klik **Deploy**.
7. Tunggu proses selesai. Vercel akan memberikan alamat website berakhiran `.vercel.app`.

### 4. Jika ingin memperbarui website
1. Edit `index.html` di komputer.
2. Buka repository GitHub.
3. Klik `index.html` → ikon pensil untuk edit langsung, atau **Add file → Upload files** untuk mengunggah versi baru.
4. Klik **Commit changes**.
5. Vercel akan otomatis melakukan deployment ulang setelah perubahan masuk ke branch yang terhubung.

## Catatan penting
- Website ini berupa website statis, sehingga tidak membutuhkan build command khusus.
- Fitur chatbot saat ini menggunakan basis pengetahuan/aturan lokal di browser, bukan model AI generatif yang terhubung ke API.
- Form pemesanan/login dan integrasi database memerlukan konfigurasi backend serta kredensial layanan yang benar sebelum digunakan untuk transaksi nyata.
- Jangan menaruh API key rahasia di dalam `index.html` atau repository GitHub.
- Tarif wisata yang belum terverifikasi ditampilkan sebagai perlu konfirmasi ke pengelola; periksa ulang tarif dan jam operasional sebelum dipublikasikan sebagai informasi resmi.
