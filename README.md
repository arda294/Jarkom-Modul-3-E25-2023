# Jarkom-Modul-2-E25-2023
Berikut adalah laporan resmi untuk pengerjaan Praktikum Modul 2 Jarkom DNS dan Webserver
## Anggota Kelompok E25
| Nama | NRP |
| --- | --- |
| Zakia Kolbi | 5025211049 |
| Ketut Arda Putra Mahotama Sadha | 5025211235 |

# Daftar Isi
- [Topologi](#topologi)
- [Konfigurasi Network Node](#konfigurasi-network-node)
- [Soal-Soal](#soal-soal)
  - [Soal 0](#soal-0)
    - [Script](#script)
    - [Hasil](#hasil)
  - [Soal 1](#soal-1)
    - [Script](#script-1)
    - [Hasil](#hasil-1)
  - [Soal 2](#soal-2)
    - [Script](#script-2)
    - [Hasil](#hasil-2)
  - [Soal 3](#soal-3)
    - [Script](#script-3)
    - [Hasil](#hasil-3)
  - [Soal 4](#soal-4)
    - [Script](#script-4)
    - [Hasil](#hasil-4)
  - [Soal 5](#soal-5)
    - [Script](#script-5)
    - [Hasil](#hasil-5)
  - [Soal 6](#soal-6)
    - [Script](#script-6)
    - [Hasil](#hasil-6)
  - [Soal 7](#soal-7)
    - [Script](#script-7)
    - [Hasil](#hasil-7)
  - [Soal 8](#soal-8)
    - [Script](#script-8)
    - [Hasil](#hasil-8)
  - [Soal 9](#soal-9)
    - [Script](#script-9)
    - [Hasil](#hasil-9)
  - [Soal 10](#soal-10)
    - [Script](#script-10)
    - [Hasil](#hasil-10)
  - [Soal 11](#soal-11)
    - [Script](#script-11)
    - [Result](#hasil-11)
  - [Soal 12](#soal-12)
    - [Script](#script-12)
    - [Result](#hasil-12)
  - [Soal 13](#soal-13)
    - [Script](#script-13)
    - [Result](#hasil-13)
  - [Soal 14](#soal-14)
    - [Script](#script-14)
    - [Result](#hasil-14)
  - [Soal 15](#soal-15)
    - [Script](#script-15)
    - [Result](#hasil-15)
  - [Soal 16](#soal-16)
    - [Script](#script-16)
    - [Result](#hasil-16)
  - [Soal 17](#soal-17)
    - [Script](#script-17)
    - [Result](#hasil-17)
  - [Soal 18](#soal-18)
    - [Script](#script-18)
    - [Result](#hasil-18)
  - [Soal 19](#soal-19)
    - [Script](#script-19)
    - [Result](#hasil-19)
  - [Soal 20](#soal-20)
    - [Script](#script-20)
    - [Result](#hasil-20)

## Topologi
![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/94e43536-77ce-47bc-9180-5041793d6c83)

## Konfigurasi Network Node
- Aura

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.49.1.0
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.49.2.0
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 10.49.3.0
	netmask 255.255.255.0

auto eth4
iface eth4 inet static
	address 10.49.4.0
	netmask 255.255.255.0  
```

- Himmel

```
auto eth0
iface eth0 inet static
	address 10.49.1.1
	netmask 255.255.255.0
	gateway 10.49.1.0
```

- Heiter

```
auto eth0
iface eth0 inet static
	address 10.49.1.2
	netmask 255.255.255.0
	gateway 10.49.1.0
```

- Denken

```
auto eth0
iface eth0 inet static
	address 10.49.2.1
	netmask 255.255.255.0
	gateway 10.49.2.0
```

- Eisen

```
auto eth0
iface eth0 inet static
	address 10.49.2.2
	netmask 255.255.255.0
	gateway 10.49.2.0
```

- Lawine

```
auto eth0
iface eth0 inet static
	address 10.49.3.1
	netmask 255.255.255.0
	gateway 10.49.3.0
```

- Linie

```
auto eth0
iface eth0 inet static
	address 10.49.3.2
	netmask 255.255.255.0
	gateway 10.49.3.0
```

- Lugner

```
auto eth0
iface eth0 inet static
	address 10.49.3.3
	netmask 255.255.255.0
	gateway 10.49.3.0
```

- Freiren

```
auto eth0
iface eth0 inet static
	address 10.49.4.1
	netmask 255.255.255.0
	gateway 10.49.4.0
```

- Flamme

```
auto eth0
iface eth0 inet static
	address 10.49.4.2
	netmask 255.255.255.0
	gateway 10.49.4.0
```

- Fern

```
auto eth0
iface eth0 inet static
	address 10.49.4.3
	netmask 255.255.255.0
	gateway 10.49.4.0
```

- Client (Sein, Stark, Revolte, Ritcher)

```
auto eth0
iface eth0 inet dhcp
```

## Soal-Soal
### Soal 0
> Setelah mengalahkan Demon King, perjalanan berlanjut. Kali ini, kalian diminta untuk melakukan register domain berupa riegel.canyon.yyy.com untuk worker Laravel dan granz.channel.yyy.com untuk worker PHP (0) mengarah pada worker yang memiliki IP [prefix IP].x.1.

Setup akan dilakukan pada node Heiter

#### Script

```
apt-get install bind9 -y

echo 'zone "riegel.canyon.e25.com" {
    type master;
    file "/etc/bind/jarkom/riegel.canyon.e25.com";
};

zone "granz.channel.e25.com" {
    type master;
    file "/etc/bind/jarkom/granz.channel.e25.com";
};

zone "3.49.10.in-addr.arpa" {
    type master;
    file "/etc/bind/jarkom/3.49.10.in-addr.arpa";
};

zone "4.49.10.in-addr.arpa" {
    type master;
    file "/etc/bind/jarkom/4.49.10.in-addr.arpa";
};' > /etc/bind/named.conf.local


mkdir /etc/bind/jarkom

echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     riegel.canyon.e25.com. root.riegel.canyon.e25.com. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@                       IN      NS      riegel.canyon.e25.com.
@                       IN      A       10.49.4.1
www                     IN      CNAME   riegel.canyon.e25.com.
;@                       IN      AAAA    ::1' > /etc/bind/jarkom/riegel.canyon.e25.com

echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     granz.channel.e25.com. root.granz.channel.e25.com. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
@                       IN      NS      granz.channel.e25.com.
@                       IN      A       10.49.3.1
www                     IN      CNAME   granz.channel.e25.com.
;@                       IN      AAAA    ::1' > /etc/bind/jarkom/granz.channel.e25.com

echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     riegel.canyon.e25.com. root.riegel.canyon.e25.com. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
4.49.10.in-addr.arpa.   IN      NS      riegel.canyon.e25.com.
1                       IN      PTR     riegel.canyon.e25.com.' > /etc/bind/jarkom/4.49.10.in-addr.arpa

echo ';
; BIND data file for local loopback interface
;
$TTL    604800
@       IN      SOA     granz.channel.e25.com. root.granz.channel.e25.com. (
                              2         ; Serial
                         604800         ; Refresh
                          86400         ; Retry
                        2419200         ; Expire
                         604800 )       ; Negative Cache TTL
;
3.49.10.in-addr.arpa.   IN      NS      granz.channel.e25.com.
1                       IN      PTR     granz.channel.e25.com.' > /etc/bind/jarkom/3.49.10.in-addr.arpa

echo "options {
        directory \"/var/cache/bind\";

        // If there is a firewall between you and nameservers you want
        // to talk to, you may need to fix the firewall to allow multiple
        // ports to talk.  See http://www.kb.cert.org/vuls/id/800113

        // If your ISP provided one or more IP addresses for stable
        // nameservers, you probably want to use them as forwarders.
        // Uncomment the following block, and insert the addresses replacing
        // the all-0's placeholder.

        // forwarders {
        //      0.0.0.0;
        // };

        //========================================================================
        // If BIND logs error messages about the root key being expired,
        // you will need to update your keys.  See https://www.isc.org/bind-keys
        //========================================================================
        //dnssec-validation auto;
        allow-query{any;};

        listen-on-v6 { any; };
};" > /etc/bind/named.conf.options

service bind9 restart
```

Dengan script ini akan setup semua dns zone yang diperlukan

#### Hasil

Ping ``riegel.canyon.e25.com``

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/dd984748-97c2-4868-9f0a-5bd71e97714f)

Ping ``granz.channel.e25.com``

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/01c0bdcc-a85c-431b-ae8f-24baad0039df)

### Soal 1
> Lakukan konfigurasi sesuai dengan peta yang sudah diberikan.

#### Script
Sudah dijawab pada [Konfigurasi Network Node](#konfigurasi-network-node)

#### Hasil
Sudah dijawab pada [Konfigurasi Network Node](#konfigurasi-network-node)

### Soal 2
> Client yang melalui Switch3 mendapatkan range IP dari [prefix IP].3.16 - [prefix IP].3.32 dan [prefix IP].3.64 - [prefix IP].3.80

Akan dibuatkan subnet sebagai berikut pada konfigurasi Himmel

#### Script

Pada Himmel
```
subnet 10.49.3.0 netmask 255.255.255.0 {
    range 10.49.3.16 10.49.3.32;
    range 10.49.3.64 10.49.3.80;
    option routers 10.49.3.0;
    option broadcast-address 10.49.3.255;
}
```

Perlu juga konfigurasi dhcp relay pada Aura (Router) agar client dapat menerima IP dari Himmel (DHCP Server)

Pada Aura
```
apt update -y
apt-get install isc-dhcp-relay -y

echo '
SERVERS="10.49.1.1"
INTERFACES="eth1 eth2 eth3 eth4"
OPTIONS=""
' > /etc/default/isc-dhcp-relay

echo '
net.ipv4.ip_forward=1
' > /etc/sysctl.conf

service isc-dhcp-relay restart
```

#### Hasil

Revolte mendapatkan IP dari Himmel

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/1e200946-cb45-495a-87e4-c65a02fda541)

### Soal 3
> Client yang melalui Switch4 mendapatkan range IP dari [prefix IP].4.12 - [prefix IP].4.20 dan [prefix IP].4.160 - [prefix IP].4.168

Akan dibuatkan subnet juga untuk switch 4

#### Script

```
subnet 10.49.4.0 netmask 255.255.255.0 {
    range 10.49.4.12 10.49.4.20;
    range 10.49.4.160 10.49.4.168;
    option routers 10.49.4.0;
    option broadcast-address 10.49.4.255;
}
```

#### Hasil

Stark mendapatkan IP dari Himmel

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/60788b68-22e9-4ad5-ac54-dae435ebaa61)

### Soal 4
> Client mendapatkan DNS dari Heiter dan dapat terhubung dengan internet melalui DNS tersebut

Ada dua cara untuk ini, dengan menggunakan script langsung untuk menambahkan ip Heiter ke ``resolv.conf`` atau dengan menggunakan DHCP server

#### Script

Resolv.conf
```
cd ~
apt update -y
apt-get -y install dnsutils
echo 'nameserver 10.49.1.2
nameserver 192.168.122.1
' > /etc/resolv.conf
apt-get -y install lynx
```

DHCP Server
```
subnet 10.49.3.0 netmask 255.255.255.0 {
    range 10.49.3.16 10.49.3.32;
    range 10.49.3.64 10.49.3.80;
    option routers 10.49.3.0;
    option broadcast-address 10.49.3.255;
    option domain-name-servers 10.49.2.2, 192.168.122.1;
}

subnet 10.49.4.0 netmask 255.255.255.0 {
    range 10.49.4.12 10.49.4.20;
    range 10.49.4.160 10.49.4.168;
    option routers 10.49.4.0;
    option broadcast-address 10.49.4.255;
    option domain-name-servers 10.49.2.2, 192.168.122.1;
}
```

Ditambahkan option domain-name-servers, sehingga akan otomatis mengisi resolv.conf ketika mendapatkan IP dari Himmel

#### Hasil

Stark ping ``google.com``

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/8ef54e1f-292b-4dad-947b-139a710a22a7)


### Soal 5
> Lama waktu DHCP server meminjamkan alamat IP kepada Client yang melalui Switch3 selama 3 menit sedangkan pada client yang melalui Switch4 selama 12 menit. Dengan waktu maksimal dialokasikan untuk peminjaman alamat IP selama 96 menit

Akan ditambahkan lease time dan max lease time pada konfigurasi tiap subnet

#### Script

```
subnet 10.49.3.0 netmask 255.255.255.0 {
    range 10.49.3.16 10.49.3.32;
    range 10.49.3.64 10.49.3.80;
    option routers 10.49.3.0;
    option broadcast-address 10.49.3.255;
    option domain-name-servers 10.49.2.2, 192.168.122.1;
    default-lease-time 180;
    max-lease-time 5760;
}

subnet 10.49.4.0 netmask 255.255.255.0 {
    range 10.49.4.12 10.49.4.20;
    range 10.49.4.160 10.49.4.168;
    option routers 10.49.4.0;
    option broadcast-address 10.49.4.255;
    option domain-name-servers 10.49.2.2, 192.168.122.1;
    default-lease-time 720;
    max-lease-time 5760;
}
```

Untuk subnet dengan IP 3.x ``default-lease-time`` akan di set 180 detik.

Untuk subnet dengan IP 4.x ``default-lease-time`` akan di set 720 detik.

Kedua subnet tersebut akan diberi ``max-lease-time`` 5760 detik.

#### Hasil

Ritcher mendapatkan IP dari Himmel

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/c6988381-e7cc-4a61-bf80-8ed37d0185d0)

Revolte mendapatkan IP dari Himmel

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/fe2921ef-e66e-4edc-b286-11c4f61b9cf5)

### Soal 6
> Pada masing-masing worker PHP, lakukan konfigurasi virtual host untuk website berikut dengan menggunakan php 7.3

Untuk ini perlu setup Nginx pada setiap worker node.

#### Script

Lawine
```
apt install nginx php7.3 php7.3-fpm wget zip htop -y

echo '
server {
    listen 80;
    server_name granz.channel.e25.com www.granz.channel.e25.com;

    location / {
        proxy_set_header Host $host;
	proxy_pass http://10.49.2.2; #IP Eisen
    }
}' > /etc/nginx/sites-available/lb-proxy

ln -s /etc/nginx/sites-available/lb-proxy /etc/nginx/sites-enabled/lb-proxy

wget -O '/var/www/jarkom.zip' 'https://drive.google.com/uc?id=1ViSkRq7SmwZgdK64eRbr5Fm1EGCTPrU1&export=download'
unzip -o /var/www/jarkom.zip -d /var/www/
rm /var/www/jarkom.zip

echo '
 server {

 	listen 8000;

 	root /var/www/modul-3;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php7.3-fpm.sock;
 	}

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
 }
' > /etc/nginx/sites-available/modul-3

ln -s /etc/nginx/sites-available/modul-3 /etc/nginx/sites-enabled/modul-3

rm /etc/nginx/sites-enabled/default

service nginx restart
service php7.3-fpm stop
service php7.3-fpm start
```

Lawine akan melakukan proxy pass ke Eisen yang akan Load Balance antara worker-worker PHP (Termasuk lawine)

Eisen
```
apt install nginx -y

echo ' # Default menggunakan Round Robin
upstream granz  {
 	server 10.49.3.1:8000; #IP Lawine
 	server 10.49.3.2:8000; #IP Linie
    	server 10.49.3.3:8000; #IP Lugner
 }

 server {
 	listen 80;
 	server_name granz.channel.e25.com www.granz.channel.e25.com;

 	location / {
        proxy_pass http://granz;
 	}
 }' > /etc/nginx/sites-available/lb-proxy

ln -s /etc/nginx/sites-available/lb-proxy /etc/nginx/sites-enabled/lb-proxy

rm /etc/nginx/sites-enabled/default

service nginx restart
```

#### Hasil

Lynx ``granz.channel.e25.com`` mendapatkan Lawine

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/1872cb13-47af-4f15-82e2-a428e6666c3a)

Request berikutnya ditangani Linie

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/50d782a4-028c-4965-8f6f-82dffa4062ee)

Request berikutnya ditangani Lugner

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/95a16b14-0446-4205-98e9-348417258e73)

### Soal 7

> Kepala suku dari Bredt Region memberikan resource server sebagai berikut:
> 
> Lawine, 4GB, 2vCPU, dan 80 GB SSD.
> Linie, 2GB, 2vCPU, dan 50 GB SSD.
> Lugner 1GB, 1vCPU, dan 25 GB SSD.
> 
> aturlah agar Eisen dapat bekerja dengan maksimal, lalu lakukan testing dengan 1000 request dan 100 request/second

Akan dilakukan apache benchmark

#### Script

```
ab -n 1000 -c 100 http://granz.channel.e25.com/
```

Apache benchmark dengan 1000 request dan 100 concurrency

#### Hasil

Dapat dilihat pada [Grimoire](https://docs.google.com/document/d/1uM2Yoy0r-yegrh4dzcmYMVLXx_rfpr16OTtRcoPNIQs/edit) kami

### Soal 8
> Karena diminta untuk menuliskan grimoire, buatlah analisis hasil testing dengan 200 request dan 10 request/second masing-masing algoritma Load Balancer dengan ketentuan sebagai berikut:
> 
> a. Nama Algoritma Load Balancer
> b. Report hasil testing pada Apache Benchmark
> c. Grafik request per second untuk masing masing algoritma. 
> d. Analisis

Akan testing untuk berbagai algoritma load balancer pada nginx

#### Script

Round Robin akan digunakan secara default nginx

- Least Connections

```
upstream granz  {
	least_conn;
 	server 10.49.3.1:8000; #IP Lawine
 	server 10.49.3.2:8000; #IP Linie
    	server 10.49.3.3:8000; #IP Lugner
}
```

- IP Hash

```
upstream granz  {
	ip_hash;
 	server 10.49.3.1:8000; #IP Lawine
 	server 10.49.3.2:8000; #IP Linie
    	server 10.49.3.3:8000; #IP Lugner
}
```

- Generic Hash

```
upstream granz  {
	hash $request_uri consistent;
 	server 10.49.3.1:8000; #IP Lawine
 	server 10.49.3.2:8000; #IP Linie
    	server 10.49.3.3:8000; #IP Lugner
}
```
	
Testing

```
ab -n 200 -c 10 http://granz.channel.e25.com/
```
Apache benchmark 200 request dengan 10 concurrency

#### Hasil

Dapat dilihat pada [Grimoire](https://docs.google.com/document/d/1uM2Yoy0r-yegrh4dzcmYMVLXx_rfpr16OTtRcoPNIQs/edit) kami

### Soal 9
> Dengan menggunakan algoritma Round Robin, lakukan testing dengan menggunakan 3 worker, 2 worker, dan 1 worker sebanyak 100 request dengan 10 request/second, kemudian tambahkan grafiknya pada grimoire.

Untuk melakukan ini, hanya perlu mematikan service nginx pada node yang ingin dimatikan (Kecuali lawine karena node ini yang proxy_pass menuju load balancer dan yang di point oleh DNS server) untuk mengurangi jumlah worker
#### Script

```
ab -n 100 -c 10 http://granz.channel.e25.com/
```

Apache benchmark 100 request dengan 10 concurrency

#### Hasil

Dapat dilihat pada [Grimoire](https://docs.google.com/document/d/1uM2Yoy0r-yegrh4dzcmYMVLXx_rfpr16OTtRcoPNIQs/edit) kami

### Soal 10
> Selanjutnya coba tambahkan konfigurasi autentikasi di LB dengan dengan kombinasi username: “netics” dan password: “ajkyyy”, dengan yyy merupakan kode kelompok. Terakhir simpan file “htpasswd” nya di /etc/nginx/rahasisakita/

Untuk ini perlu menyiapkan script yang berisi informasi untuk Auth Basic

#### Script

Informasi auth basic digenerate menggunakan WSL

Menjalankan command ``htpasswd -c .htpasswd netics`` dan memasukkan pasword yaitu ajke25

Hasilnya yaitu

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/6abbb777-68bc-404d-8530-b55ab38da2fc)

Kemudian pada Eisen
```
mkdir /etc/nginx/rahasiakita
echo 'netics:$apr1$LAhCeYuU$wvZpDE51qjEJLOug.bc4v/' > /etc/nginx/rahasiakita/.htpasswd

 server {
 	listen 80;
 	server_name granz.channel.e25.com www.granz.channel.e25.com;

	auth_basic "Authorization";
	auth_basic_user_file /etc/nginx/rahasiakita/.htpasswd;

 	location / {
        proxy_pass http://granz;
 	}
 }
```

#### Hasil

Mencoba mengakses ``granz.channel.e25.com``

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/460a7297-bd45-4a98-8a0e-17dfccf941f0)

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/10c67946-7a6e-4d70-b59f-23c4b880ce01)

Setelah memasukkan password

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/e042ec99-07dd-4d13-8a6c-496e8df50111)

### Soal 11

#### Script

#### Hasil

### Soal 12

#### Script

#### Hasil

### Soal 13

#### Script

#### Hasil

### Soal 14

#### Script

#### Hasil

### Soal 15

#### Script

#### Hasil

### Soal 16

#### Script

#### Hasil

### Soal 17

#### Script

#### Hasil

### Soal 18

#### Script

#### Hasil

### Soal 19

#### Script

#### Hasil

### Soal 20

#### Script

#### Hasil









