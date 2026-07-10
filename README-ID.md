# RizkO

RizkO adalah aplikasi jurnal trading dan analisis berbasis desktop dan mobile yang dirancang untuk membantu trader mencatat, melacak, dan menganalisis kinerja trading mereka. Dibangun menggunakan framework Avalonia UI, aplikasi ini menawarkan pengalaman yang cepat, modern, dan multi-platform.

## Fitur Utama

- **Jurnal Trading**: Catat transaksi trading harian Anda secara detail, mulai dari harga masuk/keluar, ukuran posisi, aset, status, catatan, hingga lampiran tangkapan layar (screenshot) chart.
- **Analisis Kinerja**: Pantau perkembangan akun Anda melalui grafik interaktif, termasuk grafik Cumulative PnL, Daily PnL, serta statistik pertumbuhan akun.
- **Kalkulator Trading**: Akses alat hitung bawaan untuk menghitung PnL posisi, mengevaluasi kesehatan akun, serta memproyeksikan pertumbuhan akun berdasarkan berbagai skenario.
- **Impor data Excel**: Impor riwayat transaksi langsung dari file Excel eksternal dengan pemetaan kolom yang dapat disesuaikan serta aturan deteksi penutupan transaksi yang fleksibel.
- **Dukungan Multi-Mata Uang**: Kelola akun trading dalam berbagai mata uang dengan konversi mata uang terintegrasi dan konfigurasi nilai tukar terbaru.
- **Sinkronisasi Wi-Fi Lokal**: Sinkronisasikan database jurnal dan gambar screenshot secara dua arah (bidirectional) antar perangkat (PC ke PC, PC ke Android, atau Android ke Android) yang terhubung pada jaringan lokal yang sama secara aman.
- **Berita Pasar dan RSS**: Baca berita pasar eksternal dan RSS feed langsung dari dalam aplikasi.
- **Pembaruan Otomatis**: Terima pembaruan aplikasi secara otomatis untuk distribusi standalone langsung dari GitHub.

## Cara Penggunaan

1. **Jalankan Aplikasi**: Buka file eksekutabel aplikasi (RizkO.exe pada Windows, biner yang sesuai pada Linux, atau pasang paket APK pada Android).
2. **Konfigurasi Pengaturan**: Atur mata uang utama yang ingin digunakan, opsi impor/ekspor, dan preferensi lainnya di menu Pengaturan.
3. **Kelola Akun**: Buat satu atau beberapa akun trading dengan menentukan saldo awal dan jenis mata uang.
4. **Catat Transaksi**:
   - Tambahkan transaksi secara manual melalui form Jurnal Trading, atau
   - Impor data transaksi dalam jumlah banyak sekaligus menggunakan fitur Impor Excel dengan memetakan kolom Excel Anda ke kolom aplikasi.
5. **Analisis Hasil**: Buka halaman Dashboard, Daftar Jurnal, atau Kalkulator untuk memantau metrik trading, grafik pertumbuhan, dan performa keseluruhan.

---

## Persyaratan Sistem Minimum

### Desktop (Windows & Linux)
- **Sistem Operasi**:
  - Windows: Windows 10 (Build 19041 atau lebih baru) / Windows 11
  - Linux: Ubuntu 20.04+, Debian 10+, Fedora 32+ (dengan glibc 2.27 atau lebih baru)
- **Prosesor**: Dual-core 1.6 GHz Intel/AMD atau lebih cepat
- **Memori (RAM)**: Minimal 2 GB (direkomendasikan 4 GB atau lebih)
- **Penyimpanan**: Minimal 100 MB ruang penyimpanan kosong (ukuran database SQLite dapat bervariasi tergantung jumlah jurnal dan lampiran gambar screenshot)
- **Grafis**: Kartu grafis yang mendukung Direct3D 11 / OpenGL 3.0 / Vulkan untuk akselerasi rendering antarmuka pengguna
- **Runtime**: .NET 10.0 Runtime (sudah termasuk dalam build self-contained)
- **Jaringan**: Adapter Wi-Fi/LAN aktif untuk fitur sinkronisasi lokal

### Mobile (Android)
- **Sistem Operasi**: Android 5.0 (Lollipop, API level 21) atau yang lebih baru
- **Memori (RAM)**: Minimal 1 GB (direkomendasikan 2 GB atau lebih)
- **Penyimpanan**: Minimal 50 MB ruang kosong
- **Jaringan**: Wi-Fi aktif atau Hotspot/Tethering untuk proses sinkronisasi

---

## Panduan Sinkronisasi Wi-Fi Lokal

Fitur sinkronisasi Wi-Fi lokal RizkO memungkinkan Anda untuk menyalin dan menyelaraskan seluruh catatan jurnal serta file screenshot gambar antar perangkat secara dua arah tanpa perlu menggunakan server cloud pihak ketiga.

### Prasyarat
1. Kedua perangkat harus terhubung ke **jaringan yang sama** (Wi-Fi, LAN, atau Hotspot/Tethering portabel).
2. Jika Anda menjadikan PC Windows sebagai **Host (Server)**, pastikan Windows Defender Firewall mengizinkan lalu lintas data masuk pada port `18346`. Jalankan perintah berikut di PowerShell sebagai Administrator untuk membukanya secara otomatis:
   ```powershell
   New-NetFirewallRule -DisplayName "RizkO Local Sync" -Direction Inbound -Action Allow -Protocol TCP -LocalPort 18346
   ```

### Langkah-Langkah Sinkronisasi:

#### Langkah 1: Jalankan Host (Server)
- Pada perangkat yang akan bertindak sebagai server utama (misalnya PC Anda), masuk ke menu **Sync** dari sidebar.
- Pilih peran **Host Server**.
- (Opsional) Sesuaikan Nama Perangkat dan Port pada kartu konfigurasi.
- Klik **Start Host**. Status server akan berubah menjadi *Running* (Hijau) dan memunculkan alamat IP lokal serta **Pairing PIN** 6-digit yang bersifat dinamis.

#### Langkah 2: Hubungkan Client
- Pada perangkat kedua (misalnya ponsel Android Anda), masuk ke menu **Sync**.
- Pilih peran **Connect (Client)**.
- Klik **Scan** untuk mendeteksi Host di jaringan secara otomatis, atau ketik langsung alamat IP Host yang tertera pada layar server.
- Masukkan **Pairing PIN** 6-digit dari layar server ke dalam kolom PIN di perangkat Client.
- Klik tombol **Connect & Sync**.

#### Langkah 3: Sinkronisasi Berikutnya (Perangkat Terpercaya)
- Setelah berhasil terhubung untuk pertama kali, perangkat tersebut akan terdaftar dalam **Trusted Devices** (Perangkat Terpercaya).
- Untuk sinkronisasi di masa mendatang, Anda tidak perlu lagi memasukkan PIN. Cukup aktifkan Host pada server, pilih perangkat dari daftar Host yang terdeteksi di Client, lalu klik **Connect & Sync**.
