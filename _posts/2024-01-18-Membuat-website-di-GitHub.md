---
---
---

Membuat website di GitHub dapat dilakukan dengan beberapa langkah sederhana menggunakan GitHub Pages. GitHub Pages adalah layanan yang disediakan oleh GitHub untuk membuat situs web statis secara gratis. Berikut langkah-langkahnya:

1. Buat Repository di GitHub:
Buka situs web GitHub.
Login ke akun GitHub Anda.
Klik tombol "New" untuk membuat repository baru.
Beri nama repository Anda, misalnya, "username.github.io". Pastikan nama repositori tersebut sesuai dengan format yang diperlukan oleh GitHub Pages.
2. Inisialisasi Repository:
Jika Anda memiliki file README.md, Anda dapat menghapusnya jika tidak diperlukan.
Buat file utama untuk website Anda, misalnya, index.html.
3. Commit dan Push:
Tambahkan file yang telah Anda buat ke repository lokal Anda.
bash
Copy code
git add .
Commit perubahan.
bash
Copy code
git commit -m "Inisialisasi website"
Push perubahan ke GitHub.
bash
Copy code
git push origin main
4. Aktifkan GitHub Pages:
Buka halaman repository di GitHub.
Pilih tab "Settings".
Gulir ke bawah hingga menemukan bagian "GitHub Pages".
Pilih branch sumber (umumnya main) dan simpan.
5. Akses Website:
Setelah beberapa saat, GitHub Pages akan mengaktifkan situs web Anda.
Akses situs web Anda melalui URL yang tertera di bagian "GitHub Pages" di pengaturan repository. Biasanya berupa https://username.github.io.
6. Tambahkan Konten dan Modifikasi:
Edit file HTML, CSS, atau tambahkan file lain sesuai kebutuhan.
Commit dan push perubahan Anda ke repository.
Website Anda sekarang dapat diakses melalui URL GitHub Pages yang telah ditetapkan. Perubahan yang Anda lakukan di repositori akan langsung tercermin di situs web tersebut. Jangan lupa untuk membaca dokumentasi GitHub Pages untuk informasi lebih lanjut dan penyesuaian yang dapat Anda lakukan.
