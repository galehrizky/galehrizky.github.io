---
title:  Mengurangi TIME WAIT di ubuntu.
tags: ubuntu root nginx webserver sysadmin tunning
comments: false
---

TIME_WAIT adalah salah satu status koneksi pada TCP yang digunakan untuk memastikan bahwa semua paket data yang dikirimkan oleh server sudah diterima oleh klien. Meskipun hal ini penting untuk menjaga integritas koneksi, banyak TIME_WAIT yang berlebihan dapat mempengaruhi kinerja server. Berikut adalah cara untuk mengurangi TIME_WAIT di Ubuntu:

##### Langkah 1
Edit file sysctl.conf: Buka file sysctl.conf menggunakan text editor seperti nano.

```bash 
sudo nano /etc/sysctl.conf
```

##### Langkah 2
Tambahkan baris berikut ke file sysctl.conf:

```bash 
net.ipv4.tcp_fin_timeout = 30
```
##### Langkah 3
Simpan file dan restart sistem: Simpan perubahan dan restart sistem untuk menerapkan konfigurasi baru.
```bash 
sudo sysctl -p
sudo reboot
```

Ini adalah cara untuk mengurangi TIME_WAIT di Ubuntu. Anda dapat menyesuaikan nilai fin_timeout sesuai dengan kebutuhan Anda. Namun, pastikan bahwa nilai tersebut tidak terlalu rendah karena dapat mempengaruhi integritas koneksi.