---
title:  Menggunakan SCP untuk transfer File
tags: ubuntu sysadmin  scp transfer
comments: false
---

Berikut adalah cara menggunakan SCP (Secure Copy), Anda dapat menjalankan perintah berikut:

```bash 
scp <source> <destination>
```
- `source` adalah file atau direktori yang ingin Anda salin.
- `destination` adalah lokasi tujuan file atau direktori yang ingin Anda salin.

Beberapa contoh:

* Salin file dari lokal ke remote:

```bash 
scp file.txt user@remote.example.com:/home/user/
```

* Salin direktori dari remote ke lokal:

```bash 
scp -r user@remote.example.com:/home/user/dir/ .
```

* Salin direktori dari remote ke lokal:

```bash 
scp user1@remote1.example.com:/home/user1/file.txt user2@remote2.example.com:/home/user2/
```

Catatan: Anda mungkin perlu memasukkan password akun Anda pada remote host.
