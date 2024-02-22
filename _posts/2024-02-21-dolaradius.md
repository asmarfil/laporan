Berikut langkah-langkah instalasi DaloRadius di Ubuntu dari awal hingga akhir:

Langkah 1: Persiapkan Sistem
Pastikan sistem Ubuntu Anda sudah terinstal dan terkoneksi dengan internet.

Langkah 2: Instalasi LAMP Stack
DaloRadius memerlukan lingkungan server web yang dijalankan di atas LAMP stack (Linux, Apache, MySQL, PHP). Berikut cara menginstalnya:

bash
Copy code
sudo apt update
sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql
Setelah menginstal paket-paket ini, pastikan Apache dan MySQL dijalankan:

bash
Copy code
sudo systemctl start apache2
sudo systemctl start mysql
Langkah 3: Buat Database MySQL
Buatlah database MySQL baru untuk DaloRadius:

bash
Copy code
sudo mysql -u root -p
Masukkan password MySQL Anda ketika diminta, kemudian jalankan perintah SQL berikut:

sql
Copy code
CREATE DATABASE radius;
GRANT ALL ON radius.* TO 'radius'@'localhost' IDENTIFIED BY 'password';
FLUSH PRIVILEGES;
EXIT;
Ganti 'password' dengan kata sandi yang Anda inginkan.

Langkah 4: Instalasi FreeRADIUS
Instal FreeRADIUS melalui paket manajer apt:

bash
Copy code
sudo apt install freeradius freeradius-mysql
Langkah 5: Unduh dan Instalasi DaloRadius
Unduh versi terbaru DaloRadius dari situs resminya atau repositori GitHub mereka:

bash
Copy code
wget https://github.com/lirantal/daloradius/archive/master.zip
Ekstrak file ZIP yang diunduh:

bash
Copy code
unzip master.zip
Pindahkan direktori DaloRadius ke direktori web server Anda:

bash
Copy code
sudo mv daloradius-master /var/www/html/daloradius
Langkah 6: Konfigurasi DaloRadius
Salin berkas konfigurasi contoh dan sesuaikan konfigurasi MySQL:

bash
Copy code
sudo cp /var/www/html/daloradius/library/daloradius.conf.php.sample /var/www/html/daloradius/library/daloradius.conf.php
sudo nano /var/www/html/daloradius/library/daloradius.conf.php
Edit berkas konfigurasi tersebut dengan detail yang sesuai dengan pengaturan MySQL Anda.

Langkah 7: Impor Skema Basis Data
Impor skema basis data ke dalam basis data MySQL yang telah Anda buat sebelumnya:

bash
Copy code
sudo mysql -u root -p radius < /var/www/html/daloradius/contrib/db/fr2-mysql-daloradius-and-freeradius.sql
Langkah 8: Setel Izin
Pastikan izin yang sesuai diberikan pada direktori DaloRadius:

bash
Copy code
sudo chown -R www-data:www-data /var/www/html/daloradius
sudo chmod -R 755 /var/www/html/daloradius
Langkah 9: Akses Melalui Browser
Buka browser web dan akses DaloRadius melalui alamat IP server Anda atau melalui domain (jika sudah dikonfigurasi). URL biasanya akan terlihat seperti ini:

arduino
Copy code
http://alamat_ip_server/daloradius
Langkah 10: Masukkan Kredensial
Login menggunakan kredensial default (username: administrator, password: radius). Pastikan untuk mengubah kata sandi administrator setelah login pertama Anda.

Setelah Anda berhasil masuk, Anda dapat mulai mengkonfigurasi dan menggunakan DaloRadius sesuai kebutuhan Anda.

Itulah langkah-langkah untuk menginstal DaloRadius di Ubuntu dari awal hingga akhir. Pastikan untuk selalu memperhatikan detail setiap langkah dan melakukan penyesuaian sesuai dengan kebutuhan spesifik Anda.
