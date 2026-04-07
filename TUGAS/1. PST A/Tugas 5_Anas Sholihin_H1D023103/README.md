# Scrolling text dengan I2C

## Identitas

Nama : Anas Sholihin<br>
NIM : H1D023103<br>
Mata Kuliah : Pemrograman Sistem Tertanam

## Deskripsi Proyek

Proyek ini bertujuan untuk membuat tampilan teks berjalan (scrolling text) pada layar LCD 16x2 menggunakan komunikasi I2C. Teks berjalan akan ditampilkan pada baris kedua layar LCD, sementara baris pertama akan menampilkan tulisan statis "QUOTE". Proyek ini menggunakan library Adafruit LiquidCrystal untuk mempermudah pengendalian layar LCD.

### Fitur Utama

- Baris pertama menampilkan tulisan statis "QUOTE" yang berada di tengah layar.
- Baris kedua menampilkan teks berjalan yang bergerak dari kanan ke kiri.
- Teks berjalan dapat diatur sesuai kebutuhan dengan menyesuaikan variabel `quote` di dalam kode.
- Menggunakan padding untuk menciptakan efek scrolling yang halus.

## Alat dan Bahan

1. **Arduino Uno** atau board Arduino lainnya.
2. **LCD 16x2 dengan modul I2C**: Untuk menampilkan teks.
3. **Kabel Jumper**: Untuk menghubungkan komponen.

## Simulasi dengan Tinkercad

Simulasi proyek ini dapat dilakukan menggunakan platform Tinkercad dengan langkah-langkah berikut:

1. **Buat Proyek Baru**:
   - Masuk ke akun Tinkercad dan buat proyek baru di bagian "Circuits".
2. **Tambahkan Komponen**:
   - Tambahkan Arduino Uno ke workspace.
   - Tambahkan LCD 16x2 dengan modul I2C.
   - Hubungkan pin I2C (SDA dan SCL) dari LCD ke pin Arduino (A4 untuk SDA dan A5 untuk SCL pada Arduino Uno).
   - Sambungkan pin VCC dan GND dari LCD ke pin 5V dan GND Arduino.

3. **Upload Kode**:
   - Salin kode dari file `quote.ino` ke editor kode di Tinkercad.
   - Klik tombol "Start Simulation" untuk menjalankan simulasi.

4. **Amati Hasil**:
   - Baris pertama LCD akan menampilkan teks statis "QUOTE".
   - Baris kedua akan menampilkan teks berjalan sesuai dengan kode.

Dengan simulasi ini, Anda dapat memverifikasi bahwa kode dan rangkaian bekerja sesuai dengan yang diharapkan sebelum menerapkannya pada perangkat keras.

[Buka Project](https://www.tinkercad.com/things/kGGhdDv81sh/editel?returnTo=%2Fdashboard&sharecode=M8K9Lex2uwgGW6lMdj1mVZnfVzHzCxQQGxFDCCN6pZQ)

Video:
![Video Hasil Simulasi](https://github.com/user-attachments/assets/9e2538d7-7ac1-410f-a7ee-67b59cb8733f)

## Penjelasan Kode

Kode ini terdiri dari beberapa bagian utama:

1. **Inisialisasi LCD**:
   - Menggunakan library `Adafruit_LiquidCrystal` untuk mengontrol LCD melalui I2C.
   - LCD diinisialisasi dengan ukuran 16x2.

2. **Fungsi `buatPadding`**:
   - Fungsi ini digunakan untuk membuat padding berupa spasi di awal dan akhir teks agar menciptakan efek scrolling yang halus.

3. **Variabel Global**:
   - `quote`: Berisi teks yang akan ditampilkan sebagai teks berjalan.
   - `padding`: Berisi spasi untuk efek scrolling.
   - `quoteHasil`: Kombinasi dari padding dan teks untuk scrolling.
   - `pos`: Menyimpan posisi awal teks berjalan.

4. **Fungsi `setup`**:
   - Menampilkan teks statis "QUOTE" di baris pertama.
   - Mengatur padding dan teks berjalan untuk baris kedua.

5. **Fungsi `loop`**:
   - Menampilkan teks berjalan pada baris kedua.
   - Menggeser teks dari kanan ke kiri dengan menggunakan substring dari `quoteHasil`.
   - Mengatur ulang posisi teks jika sudah selesai berjalan.

Kode ini dirancang agar fleksibel, sehingga teks yang ditampilkan dapat diubah dengan mudah hanya dengan mengganti isi variabel `quote`.
