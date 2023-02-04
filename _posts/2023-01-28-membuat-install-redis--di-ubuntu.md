---
title: install redis di Ubuntu
tags: ubuntu redis
comments: false
---

##### Install Redis
Sebelum kalian install redis di server kalian, kalian boleh mulai dulu dengan menjalankan command di bawah ini.
```bash 
galeh@lopelope:~$ sudo apt-get update
```
jika command di atas selesai kalian jalankan, kalian bisa install semua depency yang di perlukan oleh redis, dengan menjalankan command seperti ini.
```bash 
galeh@lopelope:~$ sudo apt install redis-server
```
Setelah melakukan semua proses di atas kalian bisa setting **/etc/redis/redis.conf**,  kalian harus mencari *supervised* untuk mendeklarasikan jika redis akan jalan di **systemd**, secara default setingan untuk *supervised* adalah **no**.

```bash 
galeh@lopelope:~$ sudo nano /etc/redis/redis.conf
```
file :  **/etc/redis/redis.conf**
```
# If you run Redis from upstart or systemd, Redis can interact with your
# supervision tree. Options:
#   supervised no      - no supervision interaction
#   supervised upstart - signal upstart by putting Redis into SIGSTOP mode
#                        requires "expect stop" in your upstart job config
#   supervised systemd - signal systemd by writing READY=1 to $NOTIFY_SOCKET
#   supervised auto    - detect upstart or systemd method based on
#                        UPSTART_JOB or NOTIFY_SOCKET environment variables
# Note: these supervision methods only signal "process is ready."
#       They do not enable continuous pings back to your supervisor.
supervised no
```
kalo ubah *supervised no* menjadi *supervised systemd*, lalu restart redis service menggunakan command

```bash 
galeh@lopelope:~$ sudo systemctl restart redis.service
```

##### Testing Redis
Jika kalian sudah mengikuti semua yang saya lakukan di atas, kalian bisa coba testing redis kalian di server kalian.
```bash 
galeh@lopelope:~$ sudo systemctl status redis
```
jika berhasil maka akan muncul seperti di bawah ini.
```bash 
● redis-server.service - Advanced key-value store
     Loaded: loaded (/lib/systemd/system/redis-server.service; enabled; vendor preset: enabled)
     Active: active (running) since Sat 2023-01-28 11:33:40 UTC; 12min ago
       Docs: http://redis.io/documentation,
             man:redis-server(1)
   Main PID: 91741 (redis-server)
     Status: "Ready to accept connections"
      Tasks: 5 (limit: 1030)
     Memory: 3.4M
        CPU: 1.308s
     CGroup: /system.slice/redis-server.service
             └─91741 "/usr/bin/redis-server 127.0.0.1:6379" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" "" ""

Jan 28 11:33:40 lopelope systemd[1]: Starting Advanced key-value store...
Jan 28 11:33:40 lopelope systemd[1]: Started Advanced key-value store.
```

dan untuk melakukan testing kalian perlu melakukang test *ping* menggunakan *redis-cli*

```bash 
galeh@lopelope:~$ redis-cli
```
ketika kalian melakukan *ping* dan hasil nya adalah *pong* kalian telah berhasil install redis di server kalian.
```bash 
127.0.0.1:6379> ping
PONG
127.0.0.1:6379> 
```


##### Menambahkan password di Redis

jika kalian ingin menambahkan *authetication* pada redis kalian, kita hanya perlu mengubah file config di **/etc/redis/redis.conf** 

```bash 
galeh@lopelope:~$ sudo nano /etc/redis/redis.conf
```
Kalian *uncomment* 

```bash 
# requirepass foobared
```
dan ubah menjadi seperti di bawah ini
```bash 
requirepass passwordyangdiinginkan
```
setelah mengubah password sesuai yang kalian inginkan , kalian harus restart service redis terlebih dahulu.
```bash 
galeh@lopelope:~$ sudo systemctl restart redis.service
```

untuk melakukan testing kalian harus menggunakan *redis-cli*.
```bash 
galeh@lopelope:~$ redis-cli
```
Coba login menggunakan *password* yang sudah kalian setting sebelumnya.
```bash
127.0.0.1:6379> auth passwordnya
OK
```
```bash 
127.0.0.1:6379> ping
PONG
127.0.0.1:6379> 
```





