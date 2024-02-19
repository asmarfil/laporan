Radius server adalah sebuah server yang digunakan dalam jaringan komputer untuk mengelola otentikasi, otorisasi, dan akuntansi (AAA) pengguna yang mencoba mengakses jaringan. Singkatan "RADIUS" sendiri mengacu pada Remote Authentication Dial-In User Service.

Fungsi utama dari radius server adalah untuk memverifikasi identitas pengguna yang mencoba mengakses jaringan, biasanya melalui proses autentikasi username dan password. Setelah autentikasi berhasil, radius server kemudian menentukan hak akses yang dimiliki oleh pengguna tersebut berdasarkan kebijakan yang telah ditentukan sebelumnya. Ini mencakup menentukan akses ke jaringan, pengaturan tingkat akses, dan kebijakan lainnya yang mungkin berlaku.

Radius server juga dapat digunakan untuk mengelola informasi akuntansi, seperti mencatat log waktu akses pengguna, volume data yang ditransfer, dan informasi lain yang berkaitan dengan penggunaan jaringan. Hal ini membantu administrator jaringan untuk memantau dan mengaudit aktivitas pengguna secara efektif.

Selain itu, radius server juga memungkinkan untuk integrasi dengan berbagai layanan lainnya, seperti server LDAP (Lightweight Directory Access Protocol) atau server basis data eksternal, untuk menyediakan otentikasi yang lebih kuat dan fleksibilitas dalam manajemen pengguna.

Secara umum, radius server merupakan komponen penting dalam infrastruktur jaringan yang membantu memastikan keamanan, integritas, dan manajemen yang efisien terhadap pengguna yang terhubung ke jaringan.

Instalasi MikroTik di Linux:
1. Persiapkan Perangkat Keras atau Virtual Machine:
Anda dapat menginstal MikroTik RouterOS di perangkat keras fisik atau menggunakan virtual machine seperti VMware atau VirtualBox.

2. Unduh ISO MikroTik:
Kunjungi situs web resmi MikroTik dan unduh versi ISO RouterOS yang sesuai dengan arsitektur sistem Anda (x86 atau ARM).

3. Buat VM atau Siapkan Perangkat Fisik:
Buat virtual machine baru dengan spesifikasi yang diperlukan atau siapkan perangkat fisik untuk instalasi MikroTik.

4. Boot dari ISO:
Boot virtual machine atau perangkat fisik Anda dari ISO MikroTik yang sudah diunduh.

5. Ikuti Wizard Instalasi:
Ikuti langkah-langkah dalam wizard instalasi untuk menginstal RouterOS di perangkat Anda.

6. Konfigurasi Awal:
Setelah instalasi selesai, Anda akan diminta untuk melakukan konfigurasi awal seperti menetapkan alamat IP, password, dan konfigurasi jaringan lainnya.

Instalasi Radius Server di Linux:
1. Pilih Radius Server:
Ada beberapa opsi server RADIUS yang tersedia untuk Linux, seperti FreeRADIUS atau Daloradius. Untuk panduan ini, saya akan menggunakan FreeRADIUS.

2. Instal FreeRADIUS:
Buka terminal di Linux dan instal FreeRADIUS dengan menggunakan manajer paket yang sesuai. Misalnya, untuk Ubuntu/Debian, jalankan perintah:
```sql
sudo apt-get install freeradius
```
3. Konfigurasi FreeRADIUS:
Konfigurasi FreeRADIUS sesuai dengan kebutuhan Anda. File konfigurasi utama biasanya terletak di /etc/freeradius/.

4. Tambahkan Pengguna:
Tambahkan pengguna dan atur parameter otentikasi mereka dalam file konfigurasi FreeRADIUS.

5. Mulai Layanan FreeRADIUS:
Setelah konfigurasi selesai, mulai layanan FreeRADIUS dengan perintah:
```sql
sudo systemctl start freeradius
```
6. Verifikasi:
Verifikasi bahwa FreeRADIUS berjalan dengan benar dan melayani permintaan otentikasi.
Setelah kedua aplikasi terinstal dan dikonfigurasi dengan benar, Anda dapat mengintegrasikan MikroTik dengan server RADIUS untuk otentikasi pengguna. Pastikan untuk mengacu pada dokumentasi resmi dari MikroTik dan FreeRADIUS untuk konfigurasi yang lebih rinci sesuai dengan kebutuhan Anda.
