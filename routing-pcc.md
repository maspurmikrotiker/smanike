# Metode routing 2 ISP
## contoh Topologi
### ISP 1 : 192.168.1.1
### ISP 2 : 192.168.2.1
### LAN Client : 10.0.0.1/24
# =============================

Konfigurasinya adalah sebagai berikut:
buat mark connection untuk ISP1 dulu...
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
```
,
lalu buat mark connection seperti diatas utk isp 2 seperti dibawah ini:
```bash
General:
Chain : Prerouting
in-interface: pilih interface LAN atau Client
```
,
```bash
Advance:
Per connection classifier : both address and port 2/1
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
new-connection mark : koneksi-isp2
```
,
selanjutnya buat mark routing utk isp 1 dan isp 2
```bash
General 
chain: prerouting
in-interface : pilih interface LAN atau Client
connection-mark : koneksi-isp1
```
```bash
Action
action : mark-routing 
new-routing-mark : line-ISP1
```
,
kemudian buat lagi mark routing ke isp 2
```bash
General 
chain: prerouting
in-interface : pilih interface LAN atau Client
connection-mark : koneksi-isp2
```
```bash
Action
action : mark-routing 
new-routing-mark : line-ISP2
```
