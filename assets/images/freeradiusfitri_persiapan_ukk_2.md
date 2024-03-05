
![freeradiusfitri](https://github.com/asmarfil/laporan/assets/156057446/207aa2ac-faba-4a49-bd17-3e7115539c16)

cara menginstal freeradius dengan benar 
1. pertama apdate terlebih dahulu
```sql
sudo apt update
```
2. install freeradius
```sql
sudo apt install freeradius
```
3. ```sql
   sudo service freeradius start
   ```
4. ```sql
   sudo service freeradius status
    ```
5.  ```sql
    sudo nano /etc/freeradius/3.0/users
     ```
6.  ketik ini di sela2 warna biru 
    fitri Cleartext-Password := "coba1234"
    jika selesai klik ctrl x lali klik Y terus enter 
8.  ```sql
    sudo systectl restart freeradius
     ```
9.  ```sql
    redtest fitri coba1234 localhost 0 testing123
     ```
10.  ```sql
     sudo nano /etc/freeradius/3.0/clients.conf
      ```
11.  ketik di paling bawah tulisan yg warna biru di bawah ini
     client mikrotik {
        ipaddr = 192.168.200.1
        secret = testing123
        shortname = mikrotik_client
        nastype = mikrotik
    }
jika selesai klik ctrl x lali klik Y terus enter 
    
