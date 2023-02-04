---
title:  Install postgresql di ubuntu
tags: ubuntu sysadmin amazon databse postgresql
comments: false
---

Berikut adalah cara untuk menginstall PostgreSQL pada produksi, Anda bisa mengikuti langkah-langkah berikut:

##### Langkah 1
Memperbarui package:
```bash 
sudo apt update
```

##### Langkah 2
Instal PostgreSQL:
```bash 
sudo apt install postgresql postgresql-contrib
```

##### Langkah 3
Konfigurasi database:

* Buat role baru:

```bash 
sudo -u postgres createuser --interactive
```
* Buat database baru:

```bash 
sudo -u postgres createdb mydatabase
```
 * Ubah password untuk role yang baru dibuat:

```bash 
sudo -u postgres psql
postgres=# \password myuser
```

##### Langkah 4
Restart PostgreSQL:
```bash 
sudo service postgresql restart
```