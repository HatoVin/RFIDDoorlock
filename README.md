#RFIDDOORLOCK

Project yang dibuat oleh Aulia Aufa Zahron yang dinamakan RFIDDOORLOCK ini adalah sebuah sistem keamanan sederhana yang menggunakan RFID (Radio Frequency Identification), servo motor, limit switch, dan buzzer sebagai bagian dari mekanisme akses kontrol. Berikut penjelasan komponennya:

1. **RFID (MFRC522)**: RFID digunakan untuk membaca kartu atau tag yang memiliki UID (Unique Identifier). Dalam proyek ini, dua UID diotorisasi (`authorizedUID` dan `authorizedUID2`). Sistem akan memeriksa apakah kartu yang digunakan adalah salah satu dari kartu yang diotorisasi.

2. **Servo Motor**: Servo motor mengontrol pembukaan atau penutupan pintu. Ketika akses diotorisasi, servo akan berputar untuk membuka pintu (misalnya pada posisi 90 derajat), dan ketika akses ditolak atau ditutup, servo akan kembali ke posisi awal.

3. **Limit Switch**: Limit switch digunakan untuk mendeteksi apakah pintu berada dalam posisi terbuka atau tertutup. Jika limit switch aktif (terdeteksi pintu tertutup), sistem akan mengubah status akses untuk menutup servo.

4. **Buzzer**: Buzzer digunakan sebagai indikator suara, memberikan umpan balik ketika akses diterima atau ditolak. Ada empat skenario yang diprogram untuk buzzer:
   - **"rfidC"**: Suara saat akses RFID diterima.
   - **"rfidI"**: Suara saat akses RFID ditolak.
   - **"servoC"**: Suara saat servo ditutup.
   - **"servoO"**: Suara saat servo dibuka.

5. **Proses Kerja**:
   - RFID mendeteksi kartu/tag. Jika UID yang terbaca sesuai dengan salah satu UID yang diotorisasi, sistem akan memberikan akses, membuka pintu dengan servo, dan mengeluarkan suara dengan buzzer.
   - Jika UID tidak diotorisasi, sistem akan menolak akses dan memberikan peringatan suara.
   - Limit switch berfungsi sebagai sensor untuk mendeteksi kondisi pintu (misalnya apakah tertutup), dan sistem akan menyesuaikan posisi servo berdasarkan kondisi ini.

Sistem ini dirancang untuk otomatisasi kontrol pintu menggunakan RFID sebagai metode autentikasi, di mana servo bertindak sebagai penggerak untuk membuka/menutup pintu, dan limit switch memastikan pintu tidak tetap terbuka.


Kesimpulan dari kode di atas adalah implementasi sistem akses berbasis RFID dan kontrol servo, yang juga menggunakan limit switch dan buzzer untuk memberikan umpan balik suara. Sistem ini berfungsi dengan memverifikasi UID RFID yang diizinkan. Jika UID RFID yang terdeteksi cocok dengan daftar yang diotorisasi, sistem akan membuka akses dengan menggerakkan servo dan memberikan sinyal bunyi melalui buzzer. Selain itu, sistem ini menggunakan limit switch untuk mematikan atau mengatur ulang akses. Sistem ini sangat cocok digunakan untuk kontrol akses sederhana dengan komponen yang umum seperti RFID, servo, dan buzzer.
