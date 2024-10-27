

# Dokumentasi Proyek ChatTasker

## Versi Teknologi

- **Node.js**: v20.17.0
- **npm**: v10.8.1

## Struktur Proyek

Proyek ini terdiri dari beberapa komponen yang dapat dikelola dalam repositori terpisah. Setiap komponen memiliki fungsi dan teknologi masing-masing.

### 1. Komponen Backend API

- **Repositori**: [ChatTasker-Backend](https://github.com/yourusername/ChatTasker-Backend)
- **Fungsi Utama**:

  - Mengelola tugas dan interaksi pengguna.
  - Menyimpan data di Firebase.
  - Menyediakan API untuk fitur pengingat.
- **Teknologi**:

  - Node.js
  - Express.js
  - Firebase (untuk penyimpanan tugas)
- **Fitur Utama**:

  - API CRUD untuk tugas (Create, Read, Update, Delete).
  - Pengaturan pengingat berdasarkan `dueDate` (bisa menggunakan Firebase Cloud Functions).
  - Integrasi keamanan seperti autentikasi JWT, jika aplikasi memerlukan login pengguna.

### 2. Komponen Chatbot

- **Repositori**: [ChatTasker-Chatbot](https://github.com/yourusername/ChatTasker-Chatbot)
- **Fungsi Utama**:

  - Mengelola logika interaksi chatbot dengan pengguna.
  - Memberikan respons sesuai dengan status tugas.
  - Menandai tugas sebagai selesai dan lainnya.
- **Teknologi**:

  - Dialogflow atau API chatbot lain
  - Node.js (untuk interaksi dengan Firebase)
- **Fitur Utama**:

  - Penanganan percakapan menggunakan webhook atau API yang mengarah ke server.
  - Mengirim perintah API untuk menandai tugas sebagai selesai atau mengatur pengingat.
  - Sinkronisasi dengan database Firebase untuk memeriksa status tugas pengguna.

### 3. Komponen Pengelola Pengingat

- **Repositori**: [ChatTasker-Reminder](https://github.com/yourusername/ChatTasker-Reminder)
- **Fungsi Utama**:

  - Mengirim pengingat kepada pengguna untuk tugas yang sudah mendekati tenggat waktu.
- **Teknologi**:

  - Firebase Cloud Functions atau cron jobs (misalnya dengan Node-cron)
- **Fitur Utama**:

  - Menjalankan penjadwalan untuk mengirim notifikasi ke pengguna (misalnya, melalui email atau notifikasi push).
  - Penjadwalan otomatis saat tugas baru dibuat atau tanggalnya diubah.
  - Koneksi ke database untuk mendapatkan tugas dengan `dueDate` yang mendekati.

### 4. Komponen Antarmuka Pengguna (Frontend)

- **Repositori**: [ChatTasker-Frontend](https://github.com/yourusername/ChatTasker-Frontend)
- **Fungsi Utama**:

  - Memberikan antarmuka bagi pengguna untuk berinteraksi dengan tugas dan chatbot.
- **Teknologi**:

  - Vue.js atau React
  - Firebase untuk autentikasi dan backend.
- **Fitur Utama**:

  - Tampilan daftar tugas dengan status penyelesaian.
  - Form untuk membuat dan mengedit tugas.
  - Fitur untuk chatting dengan chatbot melalui antarmuka pesan.
  - Integrasi autentikasi pengguna (opsional) menggunakan Firebase Auth.

### 5. Komponen Mobile (Opsional)

- **Repositori**: [ChatTasker-Mobile](https://github.com/yourusername/ChatTasker-Mobile)
- **Fungsi Utama**:

  - Memberikan akses melalui perangkat mobile dengan fitur manajemen tugas dan chatting dengan chatbot.
- **Teknologi**:

  - React Native atau Expo
- **Fitur Utama**:

  - Tampilan tugas dan status penyelesaian.
  - Integrasi chat dengan chatbot.
  - Sinkronisasi tugas dengan Firebase.

### 6. Komponen Integrasi dan Deployment

- **Repositori**: [ChatTasker-Deployment](https://github.com/yourusername/ChatTasker-Deployment)
- **Fungsi Utama**:

  - Menggabungkan semua komponen dan melakukan deployment ke server.
- **Teknologi**:

  - Docker (untuk containerization)
  - GitHub Actions (untuk otomatisasi CI/CD)
- **Fitur Utama**:

  - Skrip dan konfigurasi Docker untuk semua komponen.
  - Pengaturan CI/CD dengan GitHub Actions untuk otomatisasi build dan deployment ke server.
  - Dokumentasi integrasi dan panduan deployment.

### 7. Komponen Dokumentasi dan Desain

- **Repositori**: [ChatTasker-Docs](https://github.com/yourusername/ChatTasker-Docs)
- **Fungsi Utama**:

  - Menyediakan dokumentasi proyek dan panduan penggunaan untuk developer dan pengguna.
- **Teknologi**:

  - Markdown untuk dokumentasi
  - Figma atau Canva untuk desain antarmuka.
- **Fitur Utama**:

  - Dokumentasi API untuk backend.
  - Panduan penggunaan dan setup untuk setiap komponen.
  - Desain wireframe dan prototype untuk antarmuka pengguna.

---

## Cara Kerja

1. **Backend API** akan menangani semua permintaan dari frontend dan mobile, mengelola data di Firebase, serta memberikan API untuk fitur pengingat.
2. **Chatbot** berfungsi untuk berinteraksi dengan pengguna, memberikan respons yang relevan berdasarkan status tugas, dan memperbarui status tugas.
3. **Pengelola Pengingat** secara otomatis akan mengirimkan notifikasi kepada pengguna untuk tugas-tugas yang mendekati tenggat waktu, menggunakan Firebase Cloud Functions atau cron jobs.
4. **Antarmuka Pengguna** (Frontend) memungkinkan pengguna untuk berinteraksi dengan sistem melalui tampilan grafis, membuat dan mengedit tugas, serta berkomunikasi dengan chatbot.
5. **Komponen Mobile** menyediakan akses mudah bagi pengguna untuk mengelola tugas melalui perangkat mobile.
6. **Integrasi dan Deployment** memastikan bahwa semua komponen terintegrasi dengan baik dan dapat di-deploy ke server dengan mudah menggunakan Docker dan GitHub Actions.
7. **Dokumentasi dan Desain** memberikan panduan yang diperlukan untuk developer dan pengguna agar lebih memahami cara menggunakan dan mengembangkan sistem.

## Kontribusi

Pengembang yang ingin berkontribusi pada proyek ini dapat mengikuti langkah-langkah berikut:

1. Fork repositori yang relevan.
2. Buat branch baru untuk fitur atau perbaikan yang akan dikerjakan.
3. Lakukan perubahan dan buat commit.
4. Push ke branch Anda dan buat Pull Request.

## Lisensi

Proyek ini menggunakan lisensi [MIT](LICENSE).
