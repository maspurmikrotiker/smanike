# cara membuat server Moodle
# =============
### Cek nama interface
```bash
ip link
```
### Setting IP Address di Linux Ubuntu
```bash
nano /etc/netplan/00-installer-config.yaml
```
#### terus masukin syntax yaml sesuai kebutuhan di sekolah
sebagai contoh:
```bash
network:
  version: 2
  renderer: networkd
  ethernets:
    enp0s8:
      addresses: [172.16.10.11/24]
      gateway4: 172.16.10.1
      nameservers:
        addresses: [8.8.8.8, 9.9.9.9]
```
### setting timezone
```bash
timedatectl set-timezone Asia/Jakarta
```
### setting repository ke server repo ubuntu indonesia
### yg tercepat dan dekat dgn kita
```bash
nano /etc/apt/sources.list
```
#### gunakan tanda garis \ utk replace,
### 
### Instalasi web server, php, database
Panduan [a link](https://websiteforstudents.com/how-to-install-moodle-on-ubuntu-20-04-18-04-with-nginx-and-lets-encrypt/)

# Cara instan, install Web Server dan Optimasinya 

## Ubuntu/Deepin:
```bash
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && sudo bash install.sh
```
## Debian:
```bash
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh && bash install.sh
```
