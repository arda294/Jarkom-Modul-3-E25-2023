# Jarkom-Modul-3-E25-2023
Berikut adalah laporan resmi untuk pengerjaan Praktikum Modul 3 Jarkom DHCP dan Reverse Proxy
## Anggota Kelompok E25
| Nama | NRP |
| --- | --- |
| Zakia Kolbi | 5025211049 |
| Ketut Arda Putra Mahotama Sadha | 5025211235 |

# Daftar Isi
- [Topologi](#topologi)
- [Grimoire Lengkap](https://docs.google.com/document/d/1uM2Yoy0r-yegrh4dzcmYMVLXx_rfpr16OTtRcoPNIQs/edit)
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

> Lawine, 4GB, 2vCPU, dan 80 GB SSD.

> Linie, 2GB, 2vCPU, dan 50 GB SSD.

> Lugner 1GB, 1vCPU, dan 25 GB SSD.

> aturlah agar Eisen dapat bekerja dengan maksimal, lalu lakukan testing dengan 1000 request dan 100 request/second

Akan dilakukan apache benchmark

#### Script

```
ab -n 1000 -c 100 http://granz.channel.e25.com/
```

Apache benchmark dengan 1000 request dan 100 concurrency

#### Hasil

- Round Robin 1000 Requests 100 Concurrency

![1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/deb1bfbe-3c1d-4cf0-889e-6e6058caaffa)

![1 1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/2a32934e-ec3d-4d6a-9880-9052ff7bc6a0)

Diperoleh rata-rata 923.03 request per detik.

### Soal 8
> Karena diminta untuk menuliskan grimoire, buatlah analisis hasil testing dengan 200 request dan 10 request/second masing-masing algoritma Load Balancer dengan ketentuan sebagai berikut:

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

- Round Robin 200 Requests 10 Concurrency

![2](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/6e7cd046-d781-45c1-afc7-e55b1c6cd870)

![2 2](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/76e56057-03d0-4a93-9a1e-8a6a1e03ee3c)

Diperoleh rata-rata 2805.64 request per detik.

- Least Connections 200 Request 10 Concurrency

![3](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/382a5f72-7470-4682-bad4-524bb0bf6b9c)

![3 3](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/4c87b206-20be-4729-9edb-765fadbbfae5)

Diperoleh rata-rata 2248.66 request per detik.

- IP Hash 200 Requests 10 Concurrency

![4](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/71a68878-5ea0-4aa3-ab5e-06f1f709b1cb)

![4 4](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/6a91b8c5-d36e-46da-9f4c-f2eabab63e41)

Diperoleh rata-rata 2262.44 request per detik.

- Generic Hash 200 Request 10 Concurrency

![5](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/ecdf732b-0f16-4c02-9694-b4a167fad2f9)

![5 5](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/26507f18-a773-4faa-9054-898b90a366fc)

Diperoleh rata-rata 2716.91 request per detik.

### Soal 9
> Dengan menggunakan algoritma Round Robin, lakukan testing dengan menggunakan 3 worker, 2 worker, dan 1 worker sebanyak 100 request dengan 10 request/second, kemudian tambahkan grafiknya pada grimoire.

Untuk melakukan ini, hanya perlu mematikan service nginx pada node yang ingin dimatikan (Kecuali lawine karena node ini yang proxy_pass menuju load balancer dan yang di point oleh DNS server) untuk mengurangi jumlah worker
#### Script

```
ab -n 100 -c 10 http://granz.channel.e25.com/
```

Apache benchmark 100 request dengan 10 concurrency

#### Hasil

- Round Robin 3 Worker 100 Requests 10 Concurrency

![6](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/94dcaed2-452a-4fc2-b084-898de8923c9d)

![6 6](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/9d663e8a-86f5-430b-8499-2a12310bcaaa)

Diperoleh rata-rata 2550.17 request per detik.
  
- Round Robin 2 Worker 100 Requests 10 Concurrency

  ![7](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/18982b87-14e4-4ba2-9e96-ac7f448d47bf)

  ![7 7](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/d758c256-960a-45f9-822d-65fdd55de062)

Diperoleh rata-rata 2586.92 request per detik.

- Round Robin 1 Worker 100 Requests 10 Concurrency

![8](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/f4167d6d-57f5-47bc-89d9-3b3c264ebc03)

![8 8](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/879de5fd-a6cf-4a9f-9c7d-74f884f45092)

Diperoleh rata-rata 2202.11 request per detik.

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
> Lalu buat untuk setiap request yang mengandung /its akan di proxy passing menuju halaman https://www.its.ac.id.

Akan ditambahkan kondisi dimana lokasi /its akan proxy_pass menuju ``its.ac.id``

#### Script

Pada Lawine
```
server {
    listen 80;
    server_name granz.channel.e25.com www.granz.channel.e25.com;

    location /its {
        proxy_pass https://its.ac.id;
    }

    location / {
        proxy_set_header Host $host;
	proxy_pass http://10.49.2.2; #IP Eisen
    }
}
```

#### Hasil

Mencoba akses ``granz.channel.e25.com/its``

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/43feccb9-245c-4534-ba99-8c3a07c88f38)


### Soal 12
> Selanjutnya LB ini hanya boleh diakses oleh client dengan IP [Prefix IP].3.69, [Prefix IP].3.70, [Prefix IP].4.167, dan [Prefix IP].4.168.

Akan dilakukan filter IP pada Lawine

#### Script

```
geo $allowed {
    default     0;
    10.49.3.69  1;
    10.49.3.70  1;
    10.49.4.167 1;
    10.49.4.168 1;
}


server {
    listen 80;
    server_name granz.channel.e25.com www.granz.channel.e25.com;

    

    location /its {
        proxy_pass https://its.ac.id;
    }

    location / {
        proxy_set_header Host $host;
        if ($allowed) {
            proxy_pass http://10.49.2.2; #IP Eisen
        }
        proxy_pass http://127.0.0.1:8000;
    }
}
```

menggunakan modul geo nginx, bisa melakukan filter IP. IP yang eligible akan diarahkan menuju Load Balancer sedangkan yang tidak eligible akan proxy_pass ke localhost

#### Hasil

IP eligible

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/28b2a4ae-04f9-48cc-903a-214d617a9832)

Akan melalui load balancer, sehingga akan masuk ke worker-worker berbeda sesuai algoritma load balancer

IP tidak eligible

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/dd4c7ac1-2ad6-4c4d-aebd-126eff5f6b1d)

Hanya akan masuk ke Lawine

### Soal 13
> Semua data yang diperlukan, diatur pada Denken dan harus dapat diakses oleh Frieren, Flamme, dan Fern.

Akan setup database pada Denken

#### Script

```
apt-get install mariadb-server -y

echo '
[client-server]

[mysqld]
skip-networking=0
skip-bind-address
' > /etc/mysql/my.cnf

service mysql restart

echo "
CREATE USER IF NOT EXISTS 'kelompoke25'@'%' IDENTIFIED BY 'passworde25';
CREATE USER IF NOT EXISTS 'kelompoke25'@'localhost' IDENTIFIED BY 'passworde25';
CREATE DATABASE IF NOT EXISTS dbkelompoke25;
GRANT ALL PRIVILEGES ON *.* TO 'kelompoke25'@'%';
GRANT ALL PRIVILEGES ON *.* TO 'kelompoke25'@'localhost';
FLUSH PRIVILEGES;
" > ~/script.sql

mysql < ~/script.sql
```

#### Hasil

- List database pada Denken

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/d805aed6-5f35-458f-97b7-0e0283793292)

- List user database pada Denken

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/4bc9d1a6-87f3-464f-bd4d-7f8f79ef3f0d)

### Soal 14
> Frieren, Flamme, dan Fern memiliki Riegel Channel sesuai dengan quest guide berikut. Jangan lupa melakukan instalasi PHP8.0 dan Composer

Akan setup PHP8.0 dan juga Laravel

#### Script

Pada Freiren (Migrate dan juga proxy pass menuju Load Balancer)
```
rm /etc/apt/sources.list.d/php.list
apt-get update
apt install nginx php8.0 php8.0-fpm wget zip htop -y
apt-get install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2

curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'

apt-get update

apt-get install php8.0-mbstring php8.0-xml php8.0-cli php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl -y

wget https://getcomposer.org/download/2.0.13/composer.phar
chmod +x composer.phar
mv composer.phar /usr/bin/composer

echo ' # Default menggunakan Round Robin
 server {
 	listen 80;
 	server_name riegel.canyon.e25.com www.riegel.canyon.e25.com;

 	location / {
 	    proxy_pass http://10.49.2.2; #IP Eisen
        proxy_set_header HOST $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
 	}
 }' > /etc/nginx/sites-available/lb-proxy

ln -s /etc/nginx/sites-available/lb-proxy /etc/nginx/sites-enabled/lb-proxy

wget -O '/var/www/jarkom.zip' 'https://github.com/martuafernando/laravel-praktikum-jarkom/archive/refs/heads/main.zip'
unzip -o /var/www/jarkom.zip -d /var/www/
rm /var/www/jarkom.zip

echo '
APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=10.49.2.1
DB_PORT=3306
DB_DATABASE=dbkelompoke25
DB_USERNAME=kelompoke25
DB_PASSWORD=passworde25

BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

MEMCACHED_HOST=127.0.0.1

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=mt1

VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
VITE_PUSHER_HOST="${PUSHER_HOST}"
VITE_PUSHER_PORT="${PUSHER_PORT}"
VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"

JWT_SECRET=o9HWEIfemIeWt5bn8UuiMTrLQyeNsjmCRNDW7X8gRqkb3CJEEIshDjtCs2abcVcA
' > /var/www/laravel-praktikum-jarkom-main/.env

cd /var/www/laravel-praktikum-jarkom-main

composer update
php artisan migrate:fresh
php artisan db:seed --class=AiringsTableSeeder
php artisan key:generate

cd ~

echo '
 server {

 	listen 8000;

 	root /var/www/laravel-praktikum-jarkom-main/public;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php8.0-fpm.sock;
 	}

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
 }
' > /etc/nginx/sites-available/laravel-praktikum-jarkom-main

ln -s /etc/nginx/sites-available/laravel-praktikum-jarkom-main /etc/nginx/sites-enabled/laravel-praktikum-jarkom-main

chown -R www-data.www-data /var/www/laravel-praktikum-jarkom-main/storage

rm /etc/nginx/sites-enabled/default

service nginx restart
service php8.0-fpm stop
service php8.0-fpm start
```

Flamme dan Fern
```
rm /etc/apt/sources.list.d/php.list
apt-get update
apt install nginx php8.0 php8.0-fpm wget zip htop -y
apt-get install -y lsb-release ca-certificates apt-transport-https software-properties-common gnupg2

curl -sSLo /usr/share/keyrings/deb.sury.org-php.gpg https://packages.sury.org/php/apt.gpg
sh -c 'echo "deb [signed-by=/usr/share/keyrings/deb.sury.org-php.gpg] https://packages.sury.org/php/ $(lsb_release -sc) main" > /etc/apt/sources.list.d/php.list'

apt-get update

apt-get install php8.0-mbstring php8.0-xml php8.0-cli php8.0-common php8.0-intl php8.0-opcache php8.0-readline php8.0-mysql php8.0-fpm php8.0-curl -y

wget https://getcomposer.org/download/2.0.13/composer.phar
chmod +x composer.phar
mv composer.phar /usr/bin/composer

wget -O '/var/www/jarkom.zip' 'https://github.com/martuafernando/laravel-praktikum-jarkom/archive/refs/heads/main.zip'
unzip -o /var/www/jarkom.zip -d /var/www/
rm /var/www/jarkom.zip

echo '
APP_NAME=Laravel
APP_ENV=local
APP_KEY=
APP_DEBUG=true
APP_URL=http://localhost

LOG_CHANNEL=stack
LOG_DEPRECATIONS_CHANNEL=null
LOG_LEVEL=debug

DB_CONNECTION=mysql
DB_HOST=10.49.2.1
DB_PORT=3306
DB_DATABASE=dbkelompoke25
DB_USERNAME=kelompoke25
DB_PASSWORD=passworde25

BROADCAST_DRIVER=log
CACHE_DRIVER=file
FILESYSTEM_DISK=local
QUEUE_CONNECTION=sync
SESSION_DRIVER=file
SESSION_LIFETIME=120

MEMCACHED_HOST=127.0.0.1

REDIS_HOST=127.0.0.1
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_MAILER=smtp
MAIL_HOST=mailpit
MAIL_PORT=1025
MAIL_USERNAME=null
MAIL_PASSWORD=null
MAIL_ENCRYPTION=null
MAIL_FROM_ADDRESS="hello@example.com"
MAIL_FROM_NAME="${APP_NAME}"

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_USE_PATH_STYLE_ENDPOINT=false

PUSHER_APP_ID=
PUSHER_APP_KEY=
PUSHER_APP_SECRET=
PUSHER_HOST=
PUSHER_PORT=443
PUSHER_SCHEME=https
PUSHER_APP_CLUSTER=mt1

VITE_PUSHER_APP_KEY="${PUSHER_APP_KEY}"
VITE_PUSHER_HOST="${PUSHER_HOST}"
VITE_PUSHER_PORT="${PUSHER_PORT}"
VITE_PUSHER_SCHEME="${PUSHER_SCHEME}"
VITE_PUSHER_APP_CLUSTER="${PUSHER_APP_CLUSTER}"

JWT_SECRET=o9HWEIfemIeWt5bn8UuiMTrLQyeNsjmCRNDW7X8gRqkb3CJEEIshDjtCs2abcVcA
' > /var/www/laravel-praktikum-jarkom-main/.env

cd /var/www/laravel-praktikum-jarkom-main

composer update
php artisan key:generate

cd ~

echo '
 server {

 	listen 8000;

 	root /var/www/laravel-praktikum-jarkom-main/public;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php8.0-fpm.sock;
 	}

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
 }
' > /etc/nginx/sites-available/laravel-praktikum-jarkom-main

ln -s /etc/nginx/sites-available/laravel-praktikum-jarkom-main /etc/nginx/sites-enabled/laravel-praktikum-jarkom-main

chown -R www-data.www-data /var/www/laravel-praktikum-jarkom-main/storage

rm /etc/nginx/sites-enabled/default

service nginx restart
service php8.0-fpm stop
service php8.0-fpm start
```

Pada Eisen
```
upstream riegel  {
 	server 10.49.4.1:8000; #IP Frieren
 	server 10.49.4.2:8000; #IP Flamme
    	server 10.49.4.3:8000; #IP Fern
 }

server {
 	listen 80;
 	server_name riegel.canyon.e25.com www.riegel.canyon.e25.com;

 	location / {
        proxy_pass http://riegel;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	}
}
```

#### Hasil

Mencoba mengaskses ``riegel.canyon.e25.com``

![image](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/6b29ba2b-05f8-44a8-b548-9bc35230f0a9)


### Soal 15
> Riegel Channel memiliki beberapa endpoint yang harus ditesting sebanyak 100 request dengan 10 request/second. Tambahkan response dan hasil testing pada grimoire

> POST /auth/register  

Untuk testing ini dilakukan hanya pada satu worker

#### Script

payload.json
```
{"username": "test123", "password": "test123"}
```

Apache Benchmark
```
ab -n 100 -c 10 -p payload.json -T 'application/json' -H 'Accept: application/json' riegel.canyon.e25.com/api/auth/register/
```

#### Hasil

- Endpoint Register

![regis](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/a2dbdd86-d80c-42c9-b8db-13c54c9fed4b)

![regis1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/6284604b-efb2-450b-8c33-85e9eddb55ac)

Diperoleh rata-rata 220.45 request per detik.

### Soal 16
> Riegel Channel memiliki beberapa endpoint yang harus ditesting sebanyak 100 request dengan 10 request/second. Tambahkan response dan hasil testing pada grimoire

> POST /auth/login

Untuk testing ini dilakukan hanya pada satu worker

#### Script

payload.json
```
{"username": "test123", "password": "test123"}
```

Apache Benchmark
```
ab -n 100 -c 10 -p payload.json -T 'application/json' -H 'Accept: application/json' riegel.canyon.e25.com/api/auth/login/
```

#### Hasil

- Endpoint Login

![logn](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/fda51f7a-b7b0-42b4-888a-4846641337e6)

![login1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/98223011-0aa2-44d2-9e32-0861794b9214)

Diperoleh rata-rata 76.26 request per detik.

### Soal 17
> Riegel Channel memiliki beberapa endpoint yang harus ditesting sebanyak 100 request dengan 10 request/second. Tambahkan response dan hasil testing pada grimoire

> GET /me

Untuk testing ini dilakukan hanya pada satu worker

#### Script

Pertama perlu mendapatkan token yang valid pada endpoint login

curl -X POST http://riegel.canyon.e25.com/api/auth/login -H 'Accept: application/json' -H 'Content-Type: application/json' -d '{"username": "test123", "password": "test123"}' | jq

Contoh token yang didapatkan

![Login sample response](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/114855785/b7626286-d70d-4a49-8762-88d7a9cc312a)

Apache Benchmark menggunakan token yang didapatkan
```
ab -n 100 -c 10 -T 'application/json' -H 'Accept: application/json' -H 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJodHRwOi8vcmllZ2VsL2FwaS9hdXRoL2xvZ2luIiwiaWF0IjoxNzAwMDcxMTc1LCJleHAiOjE3MDAwNzQ3NzUsIm5iZiI6MTcwMDA3MTE3NSwianRpIjoiNXhudjF1MzN6NncxRUIyRyIsInN1YiI6IjEiLCJwcnYiOiIyM2JkNWM4OTQ5ZjYwMGFkYjM5ZTcwMWM0MDA4NzJkYjdhNTk3NmY3In0.n8Wef9ma2C1TtzvdeCoHk_0WOlkS0_GVPOXKuwEhfW0' riegel.canyon.e25.com/api/me/
```

#### Hasil

- Endpoint Me

![me](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/aa16a103-81af-47a1-b05f-db399c4e9d76)

![me1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/39b09030-4004-44b2-a95e-44353c092de4)

Diperoleh rata-rata 170.47 request per detik.

### Soal 18
> Untuk memastikan ketiganya bekerja sama secara adil untuk mengatur Riegel Channel maka implementasikan Proxy Bind pada Eisen untuk mengaitkan IP dari Frieren, Flamme, dan Fern.

Akan implementasi proxy_bind yang dilakukan secara otomatis oleh nginx ketika melakukan proxy_pass

#### Script

```
upstream riegel  {
 	server 10.49.4.1:8000; #IP Frieren
 	server 10.49.4.2:8000; #IP Flamme
    	server 10.49.4.3:8000; #IP Fern
 }
```

#### Hasil

Dapat dilihat pada [Grimoire](https://docs.google.com/document/d/1uM2Yoy0r-yegrh4dzcmYMVLXx_rfpr16OTtRcoPNIQs/edit) kami

### Soal 19
> Untuk meningkatkan performa dari Worker, coba implementasikan PHP-FPM pada Frieren, Flamme, dan Fern. Untuk testing kinerja naikkan 

> - pm.max_children

> - pm.start_servers

> - pm.min_spare_servers

> - pm.max_spare_servers

> sebanyak tiga percobaan dan lakukan testing sebanyak 100 request dengan 10 request/second kemudian berikan hasil analisisnya pada Grimoire.

Testing dilakukan menggunakan semua node

#### Script

Pada tiap node
```
echo '
[www]

user = www-data
group = www-data

listen = /run/php/php8.0-fpm.sock

listen.owner = www-data
listen.group = www-data



pm = dynamic
pm.max_children = 25
pm.start_servers = 7
pm.min_spare_servers = 6
pm.max_spare_servers = 10
' > /etc/php/8.0/fpm/pool.d/www.conf

service php8.0-fpm stop
service php8.0-fpm start
```

Untuk tiap percobaan dilakukan inkremen pada ``pm.max_children``, ``pm.start_servers``, ``pm.min_spare_servers``, dan ``pm.max_spare_servers``.

#### Hasil

- Percobaan 1

![19 1 1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/ff2b889b-f221-4ef6-a7b0-df776134d0d5)

![19 1 2](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/f69ae5a0-cbcd-4470-afc6-80cdc76a949c)

![19 1 3](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/73e5d83f-b01c-4796-8e8d-8acccaec2def)

Diperoleh rata-rata 92.62 request per detik.

- Percobaan 2

![19 2 1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/1737d934-4ba0-4545-b050-0b489f76e844)

![19 2 2](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/4060d7ad-5a02-4a9a-927b-fbadb16a076e)

![19 2 3](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/7bb1509d-9840-40b8-91c0-30c57e128ba8)

Diperoleh rata-rata 101.43 request per detik.

- Percobaan 3

![19 3 1](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/55c01350-67e1-4a07-8f39-04d8891b3351)

![19 3 2](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/09af6cea-b053-4783-9d4f-69ff3249d6b8)

![19 3 3](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/520c40bb-a8d4-4843-99d7-38e6c4a0fd85)

Diperoleh rata-rata 102.34 request per detik.

### Soal 20
> Nampaknya hanya menggunakan PHP-FPM tidak cukup untuk meningkatkan performa dari worker maka implementasikan Least-Conn pada Eisen. Untuk testing kinerja dari worker tersebut dilakukan sebanyak 100 request dengan 10 request/second

Hanya perlu mengubah algoritma load balancing pada Eisen

#### Script

```
upstream riegel  {
    least_conn;
 	server 10.49.4.1:8000; #IP Frieren
 	server 10.49.4.2:8000; #IP Flamme
    	server 10.49.4.3:8000; #IP Fern
 }
```

#### Hasil

- Hasil Testing Algoritma Least Connections Worker Laravel

![201](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/a57cda03-f64d-4d29-9c53-4fc8d9c3f5c4)

![202](https://github.com/arda294/Jarkom-Modul-3-E25-2023/assets/108173647/9f31daec-7717-4bf2-8880-2f552f47f8f2)

Diperoleh rata-rata 91.40 request per detik.

Hasil yang diperoleh mirip seperti hasil testing pada PHP Worker dimana Menggunakan Algoritma Round Robin memiliki waktu proses request yang lebih kecil dibandingkan menggunakan Algoritma Least Connections.






