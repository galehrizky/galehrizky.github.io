---
title: Cara install Grafana di ubuntu
tags: ubuntu root sysadmin grafana monitoring
comments: false
---

Berikut adalah beberapa cara untuk melakukan installasi Grafana di Ubuntu:


##### Langkah 1
Tambahkan repository Grafana ke sistem:
```bash 
sudo apt-get install -y software-properties-common wget
sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
```

##### Langkah 2
Perbarui cache paket dan instal Grafana:
```bash 
sudo apt-get update
sudo apt-get install grafana
```
##### Langkah 3
Jalankan Grafana:
```bash 
sudo systemctl start grafana-server
```

##### Langkah 4
Konfigurasi Grafana agar otomatis menjalankan setiap kali sistem boot:
```bash 
sudo systemctl enable grafana-server
```

Sekarang, Anda dapat mengakses Grafana melalui browser dengan mengetikkan alamat IP server atau nama host dan port 3000 (http://<server_ip>:3000). Login dengan user default admin dan password admin.