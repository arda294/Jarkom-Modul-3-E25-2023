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



#### Script

#### Hasil

### Soal 7

#### Script

#### Hasil

### Soal 8

#### Script

### Soal 9

#### Script

#### Hasil

### Soal 10

#### Script

#### Hasil

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









