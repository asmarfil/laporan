# Pengertian FreeRADIUS:
  FreeRADIUS adalah perangkat lunak server AAA open-source yang digunakan untuk memberikan layanan autentikasi, otorisasi, dan akuntansi (AAA) dalam jaringan komputer. Ini adalah proyek open-source yang didistribusikan di bawah lisensi GPL.

# Tujuan FreeRADIUS:
  1. Autentikasi: Mengonfirmasi identitas pengguna atau perangkat yang ingin mengakses jaringan.
  2. Otorisasi: Menentukan hak akses yang dimiliki oleh pengguna atau perangkat setelah berhasil diautentikasi.
  3. Akuntansi: Melacak dan mencatat penggunaan sumber daya jaringan untuk tujuan audit dan pemantauan.

# Langkah-langkah Menginstal FreeRADIUS
## update
 ```sql
  sudo apt update
```
## install aplikasi
```sql
  sudo apt install freeradius freeradius
```
## cek insalasi
```sql
  sudo systemctl stop freeradius
```
```sql
  sudo freeradius -X
```
### pastikan
# Ready to process requests

## cek servise
```sql
  sudo systemctl start freeradius
```
  ```sql
  sudo systemctl enable freeradius
```
```sql
  sudo systemctl status freeradius
``` 
## menambah user
```sql
  sudo nano /etc/freeradius/3.0/users
```
  john Cleartext-Password := "coba1234"
  simpan
  ```sql
  sudo systemctl restart freeradius
```
## mengetes
```sql
  radtest john coba1234 localhost 0 testing123
```
## menambah client nas mikrotik di free radius
```sql
  sudo nano /etc/freeradius/3.0/clients.conf
```
  client mikrotik {
  ipaddr = 192.168.200.1
  secret = testing123
  shortname = mikrotik_client
  nastype = mikrotik
}
# restart  kembali
```sql
sudo systemctl restart freeradius
```

