# cara membuat server Moodle
# =============
### Setting IP Address di Linux Ubuntu
```bash
nano /etc/netplan/00-installer-config.yaml
```
#### terus masukin syntax yaml sesuai kebutuhan di sekolah
sebagai contoh:
```bash
network:
  ethernets:
    enp0s3:
      dhcp4: true
    enp0s8:
      addresses: [172.16.10.11/24]
  version: 2
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
