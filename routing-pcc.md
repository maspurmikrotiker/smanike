# Metode routing 2 ISP
## contoh Topologi
### ISP 1 : 192.168.1.1
### ISP 2 : 192.168.2.1
### LAN Client : 10.0.0.1/24
# =============================

Konfigurasinya adalah sebagai berikut:
-Masuk ke Menu IP > Firewall > Mangle
klik add (+)
```bash
General:
Chain : Prerouting
in-interface: pilih interface LAN atau Client
```
,
```bash
Advance:
Per connection classifier : both address and port 2/0
```
,
```bash
Extra
dst address type > addr type: non local
```
,
```bash
Action
action: mark connection
new-connection mark : koneksi-isp1




