---
title: Failed building wheel for psycopg2 (Ubuntu 20.04 + Python 3.8.5 + venv)
tags: python solving problem
comments: false
---

### Masalah
Siang ini saya dapat temuan kembali, dimana saya mengalami kesulitan ketika ingin menginstall depedency *psycopg2* dan saya mendapaykan error message *Failed building wheel for psycopg2 blablabla*.

### Solusi
Setelah saya mencari jawaban di google akhir nya saya menemukan solusi nya, dengan menjalankan perintah atau command di bawah ini, issue yang saya temukan akhirnya terpecahkan ~

```bash
sudo apt-get install libpq-dev
pip3 install psycopg2
```