---
title: Cara tunning nginx di ubuntu
tags: ubuntu root nginx webserver sysadmin tunning
comments: false
---

Berikut adalah beberapa cara untuk melakukan tunning pada Nginx di Ubuntu:


##### Langkah 1
Konfigurasi worker processes: Nginx menjalankan beberapa worker process untuk menangani permintaan. Anda dapat menyesuaikan jumlah worker process sesuai dengan jumlah core yang tersedia pada server Anda. Konfigurasikan worker_processes di file nginx.conf:

```bash 
worker_processes 4;
```

##### Langkah 2
Konfigurasi worker connections: Setiap worker process dapat menangani beberapa koneksi pada saat yang bersamaan. Anda dapat menyesuaikan worker connections sesuai dengan jumlah koneksi yang diperlukan oleh aplikasi Anda. Konfigurasikan worker_connections di file nginx.conf:

```bash 
worker_connections 2048;
```
##### Langkah 3
Konfigurasi keepalive connections: Nginx dapat mempertahankan koneksi persisten antara browser dan server untuk mempercepat permintaan. Anda dapat menyesuaikan jumlah koneksi keepalive yang diperlukan oleh aplikasi Anda. Konfigurasikan keepalive_timeout di file nginx.conf:
```bash 
keepalive_timeout 65;
```

##### Langkah 4
Konfigurasi buffer size: Nginx memiliki buffer untuk menangani permintaan dan respon. Anda dapat menyesuaikan ukuran buffer sesuai dengan kebutuhan aplikasi Anda. Konfigurasikan client_body_buffer_size dan client_header_buffer_size di file nginx.conf:
```bash 
client_body_buffer_size 128k;
client_header_buffer_size 1k;
```

##### Langkah 5
Konfigurasi GZIP compression: Nginx dapat mengkompresi konten sebelum dikirim ke browser. Ini mempercepat waktu muat halaman dan menghemat bandwidth. Anda dapat mengaktifkan kompresi GZIP dengan menambahkan konfigurasi berikut di file nginx.conf:
```bash 
gzip on;
gzip_types text/plain text/css application/json application/javascript text/xml application/xml application/xml+rss text/javascript;
```

Ini adalah beberapa cara untuk melakukan tunning pada Nginx di Ubuntu. Gunakan metode yang sesuai dengan kebutuhan aplikasi Anda dan uji performa secara berkala untuk memastikan bahwa konfigurasi yang Anda lakukan memiliki hasil yang diinginkan.
