---
title:  Setting Fail2ban di ubuntu
tags: ubuntu root fail2ban ddos
comments: false
---

Fail2ban adalah perangkat lunak pencegahan intrusi populer yang membantu melindungi server Anda dari serangan yang merugikan, seperti usaha login brute-force. Berikut adalah langkah-langkah umum untuk mengatur Fail2ban pada server Anda:

##### Langkah 1
Instal Fail2ban: Fail2ban biasanya tersedia melalui manajer paket dari distribusi Linux Anda. Anda dapat menginstalnya menggunakan perintah berikut pada Debian/Ubuntu:

```bash 
sudo apt-get install fail2ban
```

##### Langkah 2
Konfigurasi jail.local: Jail.local adalah berkas konfigurasi di mana Anda dapat mengatur aturan kustom untuk Fail2ban. Anda dapat menyalin berkas jail.conf default ke jail.local, dan membuat perubahan di sana.

```bash 
sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local
```
##### Langkah 3
Tentukan Jail: Jail adalah set aturan untuk Fail2ban untuk mengikuti layanan tertentu. Anda dapat menentukan penjara untuk SSH dengan menambahkan kode berikut ke jail.local:

```bash 
[ssh]
enabled  = true
port     = ssh
filter   = sshd
logpath  = /var/log/auth.log
maxretry = 6
```

##### Langkah 4
Tentukan waktu banned: Anda dapat menentukan waktu banned untuk setiap penjara dalam detik. Waktu banned default adalah 10 menit (600 detik).

```bash 
bantime = 600
```

##### Langkah 5
Mulai Fail2ban: Setelah membuat perubahan pada jail.local, Anda dapat memulai Fail2ban dengan perintah berikut:
```bash 
sudo systemctl start fail2ban
```

##### Langkah 6
Verifikasi Konfigurasi: Anda dapat menggunakan perintah berikut untuk memeriksa status Fail2ban dan memverifikasi bahwa telah dikonfigurasi dengan benar:
```bash 
sudo fail2ban-client status ssh
```

Inilah langkah-langkah dasar untuk mengatur Fail2ban pada server Anda. Anda dapat mengkonfigurasi layanan lain atau membuat penjara tambahan dengan cara yang sama. Penting untuk memantau log server Anda dan log Fail2ban untuk memastikan bahwa berfungsi seperti yang diharapkan.
