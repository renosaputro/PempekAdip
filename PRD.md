# PRD.md --- PempekAdip

**Nama Produk:** PempekAdip\
**Jenis Produk:** Website informasi, promosi, dan pemesanan online\
**Pemilik Usaha:** Adip\
**Bidang Usaha:** Kuliner khas Palembang\
**Versi:** 1.0\
**Status:** Pedoman pengembangan awal

------------------------------------------------------------------------

## 1. Deskripsi Produk

PempekAdip adalah website untuk memperkenalkan usaha pempek khas
Palembang milik Adip kepada masyarakat. Website menyediakan informasi
usaha, katalog produk, pemesanan online, lokasi, berita, serta asisten
virtual berbasis AI untuk membantu menjawab pertanyaan pelanggan.

Website harus sederhana, menarik, responsif, mudah digunakan, dan mudah
dikembangkan.

## 2. Tujuan

1.  Memperkenalkan PempekAdip kepada calon pelanggan.
2.  Menampilkan produk, deskripsi, dan harga.
3.  Memudahkan pelanggan menghubungi penjual dan melakukan pemesanan.
4.  Menyediakan informasi profil usaha, lokasi, dan berita.
5.  Membantu pelanggan mendapatkan informasi melalui Adip AI Assistant.

## 3. Target Pengguna

-   **Pengunjung:** mencari informasi tentang PempekAdip.
-   **Calon pelanggan:** melihat produk dan harga serta bertanya kepada
    AI.
-   **Pelanggan:** melakukan pemesanan dan menghubungi penjual.
-   **Admin/pemilik:** mengelola produk, berita, dan informasi website.

## 4. Navigasi dan Fitur Utama

Website memiliki lima menu navigasi utama.

### 4.1 Beranda

-   Menampilkan logo dan identitas PempekAdip.
-   Hero section berisi foto pempek, headline, dan deskripsi singkat.
-   Tombol menuju halaman Pesan Online.
-   Menampilkan beberapa produk unggulan.
-   Menampilkan ringkasan keunggulan usaha.
-   Menampilkan informasi kontak dan footer.

### 4.2 Pesan Online

-   Menampilkan daftar produk pempek.
-   Setiap produk memiliki foto, nama, deskripsi, dan harga.
-   Pelanggan dapat memilih produk dan jumlah pesanan.
-   Menampilkan ringkasan pesanan dan total harga.
-   Pelanggan mengisi nama, nomor WhatsApp, alamat atau pilihan
    pengambilan, serta catatan.
-   Pesanan diteruskan kepada penjual, untuk versi awal melalui
    WhatsApp.

Harga dan informasi produk harus berasal dari data resmi yang dikelola
admin. Sistem harus memvalidasi harga dan ketersediaan di backend
sebelum pesanan dikirim.

### 4.3 Tentang Adip

-   Menampilkan profil usaha dan pemilik.
-   Menampilkan cerita atau sejarah PempekAdip.
-   Menampilkan komitmen dan informasi usaha.
-   Menggunakan foto yang disetujui pemilik.

### 4.4 Lokasi

-   Menampilkan alamat lengkap PempekAdip.
-   Menampilkan peta atau tautan Google Maps.
-   Menampilkan jam operasional dan kontak.
-   Menyediakan tombol petunjuk arah.

Alamat, jam operasional, dan titik peta harus dikonfirmasi oleh pemilik
sebelum dipublikasikan.

### 4.5 Berita

-   Menampilkan daftar artikel atau informasi terbaru.
-   Setiap artikel memiliki judul, gambar, tanggal, ringkasan, dan isi.
-   Pengunjung dapat membuka halaman detail berita.
-   Konten berita dikelola oleh admin.

## 5. Fitur AI: Adip AI Assistant

### 5.1 Tujuan

Adip AI Assistant adalah chatbot pada website yang membantu pelanggan
mendapatkan informasi tentang PempekAdip melalui percakapan bahasa
alami.

Chatbot dapat diakses melalui tombol chat yang tampil pada halaman
website.

### 5.2 Kemampuan AI

Adip AI Assistant dapat:

-   Menjawab pertanyaan umum tentang PempekAdip.
-   Menjelaskan produk yang tersedia.
-   Memberikan informasi harga berdasarkan data produk.
-   Menjelaskan cara pemesanan.
-   Memberikan informasi alamat dan jam operasional.
-   Mengarahkan pelanggan ke halaman Pesan Online atau kontak penjual.

### 5.3 Batasan AI

-   AI hanya menjawab berdasarkan informasi PempekAdip yang tersedia dan
    telah diverifikasi.
-   AI tidak boleh mengarang nama produk, harga, stok, alamat, promo,
    atau jam operasional.
-   Jika informasi tidak tersedia, AI harus menyampaikan bahwa informasi
    belum tersedia dan menyarankan pelanggan menghubungi penjual.
-   AI tidak mengonfirmasi pembayaran atau pesanan sebagai pesanan
    berhasil.
-   Pemesanan tetap dilakukan melalui alur Pesan Online dan dikonfirmasi
    oleh penjual.
-   AI bukan fitur rekomendasi produk otomatis atau sistem analisis
    ulasan pada versi awal.

### 5.4 Alur Kerja AI

1.  Pengunjung membuka chatbot.
2.  Pengunjung mengirim pertanyaan.
3.  Frontend React mengirim pesan ke backend Node.js.
4.  Backend mengambil informasi relevan dari MySQL.
5.  Backend mengirim pertanyaan dan konteks informasi ke Gemini API.
6.  Gemini menghasilkan jawaban berdasarkan konteks tersebut.
7.  Backend mengirim jawaban ke frontend.
8.  Chatbot menampilkan jawaban kepada pelanggan.

### 5.5 Keamanan AI

-   Gemini API Key hanya disimpan di backend melalui file environment
    (`.env`).
-   API Key tidak boleh ditulis di kode React atau dikirim ke browser.
-   Backend memvalidasi input dan membatasi ukuran pesan.
-   Jangan mengirim data pribadi pelanggan yang tidak diperlukan ke
    layanan AI.
-   Terapkan batas penggunaan (rate limit) untuk mengurangi
    penyalahgunaan dan biaya API.
-   Tampilkan pemberitahuan bahwa jawaban diberikan oleh AI dan dapat
    perlu dikonfirmasi kepada penjual.

## 6. Teknologi yang Digunakan

  -----------------------------------------------------------------------
  Bagian                  Teknologi               Kegunaan
  ----------------------- ----------------------- -----------------------
  Frontend                React.js                Antarmuka website

  Styling                 CSS                     Tampilan dan responsif

  Backend                 Node.js + Express.js    API dan logika aplikasi

  Database                MySQL                   Menyimpan produk,
                                                  berita, dan pesanan

  AI                      Google Gemini API       Menjawab pertanyaan
                                                  chatbot

  Peta                    Google Maps / tautan    Informasi lokasi
                          Maps                    

  Integrasi pesanan       WhatsApp link           Mengirim detail pesanan
                                                  ke penjual

  Version control         Git dan GitHub          Pengelolaan kode
  -----------------------------------------------------------------------

Versi dan dependensi paket ditentukan saat setup proyek. Gunakan versi
stabil yang kompatibel dan catat dependensi di `package.json`.

## 7. Arsitektur Sistem

``` text
PENGUNJUNG
    |
    v
REACT.JS (FRONTEND)
    |
    v
NODE.JS + EXPRESS (BACKEND API)
    |
    +-----------> MYSQL DATABASE
    |              - Produk
    |              - Berita
    |              - Pesanan
    |              - Informasi usaha
    |
    +-----------> GOOGLE GEMINI API
                   - Adip AI Assistant
    |
    v
RESPONS KE WEBSITE
```

Semua akses ke MySQL dan Gemini API dilakukan melalui backend. React
tidak mengakses database secara langsung dan tidak menyimpan API Key AI.

## 8. Rancangan Database Awal

Database menggunakan MySQL. Tabel utama:

### 8.1 `admins`

Menyimpan akun admin.

-   `id` --- primary key
-   `name` --- nama admin
-   `email` --- email login, unik
-   `password_hash` --- password yang sudah di-hash
-   `created_at`
-   `updated_at`

### 8.2 `products`

Menyimpan katalog produk.

-   `id` --- primary key
-   `name` --- nama produk
-   `description` --- deskripsi
-   `price` --- harga
-   `image_url` --- lokasi gambar
-   `is_available` --- status ketersediaan
-   `created_at`
-   `updated_at`

### 8.3 `news`

Menyimpan artikel berita.

-   `id` --- primary key
-   `title` --- judul
-   `slug` --- identitas URL, unik
-   `summary` --- ringkasan
-   `content` --- isi artikel
-   `image_url` --- gambar
-   `status` --- draft atau published
-   `published_at`
-   `created_at`
-   `updated_at`

### 8.4 `orders`

Menyimpan informasi pesanan.

-   `id` --- primary key
-   `customer_name` --- nama pelanggan
-   `phone` --- nomor WhatsApp
-   `delivery_address` --- alamat atau keterangan pengambilan
-   `notes` --- catatan
-   `total_price` --- total pesanan
-   `status` --- status pesanan
-   `created_at`

### 8.5 `order_items`

Menyimpan rincian produk pada pesanan.

-   `id` --- primary key
-   `order_id` --- foreign key ke `orders`
-   `product_id` --- foreign key ke `products`
-   `product_name` --- nama produk saat dipesan
-   `unit_price` --- harga saat dipesan
-   `quantity` --- jumlah
-   `subtotal` --- total item

Harga dan nama produk disalin ke rincian pesanan agar riwayat transaksi
tetap benar ketika katalog berubah.

Informasi profil, alamat, jam operasional, dan kontak dapat disimpan
pada tabel `business_info` atau dikelola melalui konfigurasi admin.
Riwayat percakapan AI tidak wajib disimpan pada versi awal.

## 9. Kebutuhan Admin

Admin perlu dapat:

-   Login dan logout.
-   Menambah, mengubah, dan menghapus produk.
-   Mengubah harga dan ketersediaan produk.
-   Menambah, mengubah, menerbitkan, dan menghapus berita.
-   Memperbarui profil, alamat, jam operasional, dan kontak usaha.
-   Melihat pesanan yang masuk jika penyimpanan pesanan diaktifkan.

Akses halaman dan API admin harus dilindungi autentikasi serta
otorisasi.

## 10. Kebutuhan Nonfungsional

-   **Responsif:** dapat digunakan pada desktop, tablet, dan ponsel.
-   **Performa:** gambar dioptimalkan dan halaman tidak memuat aset
    berlebihan.
-   **Keamanan:** validasi input, proteksi akses admin, dan penyimpanan
    rahasia di backend.
-   **Kemudahan penggunaan:** navigasi jelas dan proses pemesanan mudah
    dipahami.
-   **Pemeliharaan:** kode frontend dan backend dipisahkan dan
    terstruktur.
-   **Kompatibilitas:** mendukung browser modern.
-   **SEO:** setiap halaman penting memiliki judul, deskripsi, dan
    struktur konten yang baik.

## 11. Struktur Proyek yang Disarankan

``` text
pempekadip/
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── assets/
│   │   └── App.jsx
│   └── package.json
│
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── middleware/
│   │   └── app.js
│   ├── .env
│   └── package.json
│
├── database/
│   └── schema.sql
│
├── PRD.md
└── README.md
```

Struktur ini merupakan rancangan awal dan dapat disesuaikan saat
implementasi.

## 12. Tahapan Pengembangan

1.  **Persiapan:** membuat repository, struktur proyek, dan konfigurasi
    React, Node.js, serta MySQL.
2.  **Desain:** membuat rancangan tampilan lima halaman utama.
3.  **Frontend:** mengimplementasikan Beranda, Pesan Online, Tentang
    Adip, Lokasi, dan Berita.
4.  **Backend dan database:** membuat API, tabel MySQL, serta koneksi
    backend.
5.  **Pemesanan:** membuat keranjang, ringkasan pesanan, dan pengiriman
    pesanan melalui WhatsApp.
6.  **Admin:** membuat login dan pengelolaan produk, berita, serta
    informasi usaha.
7.  **AI:** mengintegrasikan Adip AI Assistant dengan Gemini API dan
    informasi resmi dari database.
8.  **Pengujian:** menguji fungsi, tampilan responsif, keamanan, dan
    alur chatbot.
9.  **Deployment:** menerbitkan frontend, backend, dan database ke
    lingkungan hosting.

## 13. Acceptance Criteria

Website versi awal dianggap memenuhi kebutuhan apabila:

-   Lima menu navigasi utama tersedia dan berfungsi.
-   Informasi profil dan produk dapat ditampilkan.
-   Pelanggan dapat melihat harga dan membuat ringkasan pesanan.
-   Pelanggan dapat meneruskan pesanan kepada penjual melalui WhatsApp.
-   Halaman lokasi menampilkan informasi yang telah diverifikasi.
-   Halaman berita dapat menampilkan artikel.
-   Admin dapat mengelola produk dan berita.
-   Adip AI Assistant dapat menerima pertanyaan dan menampilkan jawaban.
-   Jawaban AI menggunakan informasi PempekAdip yang tersedia dan tidak
    mengarang data.
-   API Key Gemini tidak dapat diakses dari frontend.
-   Website dapat digunakan pada perangkat desktop dan mobile.

## 14. Aturan Pengembangan dan Pemanfaatan AI

-   Jadikan dokumen PRD ini sebagai acuan utama pengembangan.
-   Gunakan React.js untuk frontend, Node.js + Express.js untuk backend,
    dan MySQL untuk database.
-   Jangan mengganti teknologi utama tanpa persetujuan.
-   Pisahkan kode berdasarkan fungsi dan tanggung jawab.
-   Sebelum mengubah kode, periksa struktur dan implementasi yang sudah
    ada.
-   Berikan kode lengkap beserta lokasi file dan langkah menjalankannya.
-   Jangan menghapus atau mengubah fitur yang sudah berjalan tanpa
    alasan.
-   Uji setiap fitur setelah implementasi.
-   Gunakan data produk dan informasi usaha yang telah dikonfirmasi
    pemilik.
-   Simpan API Key dan kredensial database di environment variables.
-   Jangan membuat data produk, harga, alamat, atau informasi usaha
    fiktif untuk ditampilkan sebagai fakta.

## 15. Batasan Versi Awal

Fokus versi awal adalah website informasi dan pemesanan sederhana dengan
satu fitur AI, yaitu Adip AI Assistant.

Fitur berikut belum termasuk ruang lingkup versi awal: - Pembayaran
otomatis/payment gateway. - Pelacakan pengiriman. - Aplikasi mobile. -
AI rekomendasi produk khusus. - AI pembuat paket otomatis. - AI analisis
ulasan. - AI pengenalan gambar. - Program loyalitas pelanggan.

Fitur tambahan dapat dipertimbangkan setelah versi awal berjalan dan
dievaluasi.

------------------------------------------------------------------------

**Arah Produk:** PempekAdip menjadi website resmi usaha pempek khas
Palembang milik Adip yang menyediakan informasi usaha, katalog produk,
pemesanan online, lokasi, berita, dan asisten virtual AI untuk membantu
pelanggan.
