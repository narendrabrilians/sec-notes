# Firewalls & IDS (Intrusion Detection System)

## 🔥 Firewall

**Firewall** adalah sistem keamanan jaringan yang **mengontrol lalu lintas masuk dan keluar** berdasarkan aturan yang ditentukan.

**Tujuan**: Memblokir akses tidak sah ke atau dari jaringan.

### Contoh fungsi:
- Memblokir port 22 (SSH) dari publik.
- Hanya mengizinkan HTTP/HTTPS dari internet.

### Jenis-jenis:
- **Network Firewall**: di level jaringan (contoh: Cisco ASA, `iptables`)
- **Host-based Firewall**: untuk satu perangkat (contoh: Windows Defender Firewall)

## 🕵️ IDS (Intrusion Detection System)

**IDS** adalah sistem yang **mendeteksi aktivitas mencurigakan** di jaringan atau sistem, lalu memberikan **peringatan (alert)**. IDS **tidak memblokir**, hanya mendeteksi.

### Contoh fungsi:
- Mendeteksi scanning port dari attacker.
- Menemukan pola serangan seperti SQL Injection.

### Jenis-jenis:
- **NIDS** (Network-based IDS): memantau lalu lintas jaringan.
- **HIDS** (Host-based IDS): memantau aktivitas di dalam satu host.
