---
title: Melakukan reverse proxy nginx di ubuntu
tags: ubuntu root nginx webserver sysadmin tunning proxy
comments: false
---

Untuk melakukan reverse proxy pada Nginx di Ubuntu, ikuti langkah-langkah berikut:


##### Langkah 1
Instal Nginx: Pastikan bahwa Nginx sudah terinstall pada server Anda. Anda dapat menginstall Nginx melalui terminal dengan mengetik perintah berikut:

```bash 
sudo apt-get update
sudo apt-get install nginx
```

##### Langkah 2
Buat Virtual Host baru: Buat file baru yang mengkonfigurasi virtual host baru untuk reverse proxy Anda. Biasanya file ini disimpan di direktori /etc/nginx/sites-available. Misalnya, jika Anda ingin membuat reverse proxy untuk situs example.com, buat file baru bernama example.com.

```bash 
sudo nano /etc/nginx/sites-available/example.com
```
##### Langkah 3
Konfigurasi Virtual Host: Tambahkan konfigurasi berikut ke dalam file virtual host baru Anda. Konfigurasi ini akan meneruskan semua permintaan dari example.com ke IP address atau hostname tertentu.
```bash 
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://your-server;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```

##### Langkah 4
Buat symbolic link: Buat symbolic link dari file virtual host baru Anda ke direktori /etc/nginx/sites-enabled.

```bash 
sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
```

##### Langkah 5
Tes konfigurasi: Tes konfigurasi Nginx untuk memastikan bahwa tidak ada kesalahan.
```bash 
sudo nginx -t
```

##### Langkah 6
Restart Nginx: Restart Nginx untuk menerapkan konfigurasi baru.
```bash 
sudo systemctl restart nginx
```

Ini adalah cara untuk melakukan reverse proxy pada Nginx di Ubuntu. Periksa dokumentasi Nginx untuk mengetahui lebih lanjut tentang cara mengkonfigurasi reverse proxy.
