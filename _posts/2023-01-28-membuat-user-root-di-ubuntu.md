---
title:  Membuat user root di ubuntu
tags: ubuntu root
comments: false
---

Hallo setelah sekian lama saya tidak mencoba menulis sebuah tutorial, kali ini saya akan  share sedikit ilmu yang saya miliki yaitu **cara menambahkan user root di ubuntu.**

##### Menambakan user
Sebelum kalian membuat user pada operation system ubuntu, kalian harus memiki user dengan privilege sebagai root terlebih dahulu.

```bash 
root@lopelope:~# adduser galeh
```
Kalian isi semua form di bawah seperti new password sebagai password  dan informasi lain nya yang akan di gunakan oleh kalian nanti.
```bash 
Adding user `galeh' ...
Adding new group `galeh' (1003) ...
Adding new user `galeh' (1003) with group `galeh' ...
Creating home directory `/home/galeh' ...
Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for galeh
Enter the new value, or press ENTER for the default
	Full Name []: 
	Room Number []: 
	Work Phone []: 
	Home Phone []: 
	Other []: 
Is the information correct? [Y/n] 

```
##### Menambakan user sebagai root
jika sudah selesai, kalian tinggal menabahkan user tersebut sebagai root, dengan menjalankan command di bawah ini .

```bash 
root@lopelope:~# usermod -aG sudo galeh
```
