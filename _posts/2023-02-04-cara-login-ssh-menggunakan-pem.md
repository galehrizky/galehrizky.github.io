---
title: Cara Login ssh menggunakan PEM Amazon
tags: ubuntu sysadmin amazon scp login
comments: false
---

Berikut adalah cara untuk login ke server menggunakan private key AWS (Amazon Web Services), Anda dapat menjalankan perintah berikut:

```bash 
ssh -i /path/to/private-key.pem ubuntu@<server-ip>
```
- `/path/to/private-key.pem` adalah lokasi file private key Anda.
- `ubuntu` adalah nama pengguna pada server.
- `server-ip` adalah alamat IP server yang ingin Anda akses.


Pastikan bahwa file private key Anda memiliki hak akses yang tepat (permission 0400) agar tidak dapat dibaca oleh pihak lain. Anda juga bisa menambahkan opsi -v untuk melihat detail koneksi SSH.

contoh:

```bash 
ssh -i ~/keys/my-aws-key.pem -v ubuntu@54.0.1.2
```