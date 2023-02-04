---
title: Cara install Django
tags: django python
comments: false
---

Hallo karena akhir - akhir ini saya harus menggunakan django, saya memutuskan untuk membuat catatan ini agar tidak lupa.
Beberapa hal yang perlu di siapkan sebelum install django adalah :
1. Python3 
2. virtualenv
3. pip3

### install django
Setelah berhasil install semua yang butuhkan  yang perlu di lakukan adalah membuat virtualenv dan masuk ke dalam virtualenv dengan command berikut 

```bash
virtualenv django-test
source django-test/bin/active
```
jika berhasil masuk ke dalam virtualenv, terminal yang di pakai akan seperti di bawah ini
```bash
(django-test) user@localhost django 
```
setelah semua step di atas telah di lakukan, kalian bisa install django dengan command berikut
```bash
pip3 install django 
```

### menggunakan django admin
Sekarang kita akan mencoba menggunakan django-admin, yaitu fitur bawaan dari django itu sendiri.

```bash
django-admin startproject mysite
```
maka akan secara otomatis meng-generate beberapa files seperti di bawah ini 
```
├── manage.py
└── mysite
    ├── __init__.py
    ├── asgi.py
    ├── settings.py
    ├── urls.py
    └── wsgi.py
```
setiap file yang di generate di atas memiliki fungsi nya masing-masing, mungkin di catatan berikut nya saya akan tambahkan fungsi dari setiap file di atas, kita coba lanjut ke step berikut nya, jika kalian berhasil meng-generate semua file di atas kita coba running project django kita dengan command di bawah

```
python3 manage.py runserver
```
secara default port yang di gunakan oleh django adalah port 8000, dan kalian bisa coba akses di url *http://localhost:8000/*, maka akan tampil seperti gambar di bawah ini.

<img src="/assets/img/post/django.png">
