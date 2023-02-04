---
title: install nginx di ubuntu
tags: ubuntu root nginx webserver sysadmin
comments: false
---

Berikut adalah cara untuk menginstal Nginx di Ubuntu:

##### Langkah 1
Memperbarui Repository: Pastikan bahwa repository sistem Anda sudah dimutakhirkan dengan menjalankan perintah berikut:

```bash 
sudo apt update
```

##### Langkah 2
Instal Nginx: Anda dapat menginstal Nginx menggunakan perintah berikut:

```bash 
sudo apt install nginx
```
##### Langkah 3
Memulai Nginx: Setelah menginstal Nginx, mulai layanannya dengan menjalankan perintah berikut:
```bash 
sudo systemctl start nginx
```

##### Langkah 4
Konfigurasi Firewall: Jika firewall sedang berjalan, pastikan untuk membuka port 80 agar Nginx dapat diakses melalui jaringan:

```bash 
sudo ufw allow 'Nginx HTTP'
```

##### Langkah 5
Verifikasi Instalasi: Buka browser dan akses alamat IP server Anda. Anda harus melihat halaman default Nginx. Jika Anda melihat halaman page Nginx, Nginx berhasil diinstal dan dijalankan.


Ini adalah cara untuk menginstal Nginx di Ubuntu. Anda sekarang dapat memulai mengonfigurasi dan mengoptimalkan Nginx sesuai kebutuhan aplikasi Anda.
