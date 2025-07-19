# 🧭 5 Tahapan Penetration Testing

## 🕵️ Reconnaissance & Information Gathering

Tahap awal untuk mengumpulkan sebanyak mungkin informasi tentang target.

### ▸ Passive Reconnaissance
- Tanpa interaksi langsung ke target
- Contoh: Google Dorking, Whois, Shodan, OSINT

### ▸ Active Reconnaissance
- Melibatkan interaksi langsung ke target (bisa terdeteksi)
- Contoh: Nmap, ping, port scanning, subdomain brute-force

## 🔍 Scanning

Proses mendeteksi dan memetakan sistem target untuk menemukan port, layanan, dan potensi kerentanan.

### Contoh kegiatan:
- **Port Scanning** — Menemukan port terbuka (misalnya: `nmap`)
- **Service Detection** — Mengidentifikasi layanan di balik port
- **Vulnerability Scanning** — Mendeteksi kerentanan (misalnya: `Nessus`, `OpenVAS`)

## 🎯 Exploitation & Gaining Access

Menyerang target dengan memanfaatkan celah keamanan untuk memperoleh akses tidak sah.

### Contoh serangan:
- SQL Injection
- XSS
- RCE
- Brute Force

### Tools:
- `Metasploit`, `SQLmap`, `Burp Suite`, `Hydra`, custom script

## 🔐 Maintaining Access

Menjaga agar akses yang telah diperoleh tetap tersedia meskipun sistem di-restart atau diperbaiki.

### Teknik:
- Backdoor, webshell
- Akun user tersembunyi
- SSH key injection
- Cronjob untuk koneksi otomatis

### Tools:
- `Netcat`, `Metasploit persistence`, custom script (Python, Bash, PHP)

## 🧹 Covering Tracks

Menghapus jejak agar aktivitas tidak terdeteksi oleh administrator atau sistem monitoring.

### Contoh:
- Menghapus log file
- Mengubah `.bash_history`
- Menjalankan perintah langsung dari memory (menghindari jejak file di disk)
- Menggunakan rootkit untuk menyembunyikan proses, file, atau aktivitas jaringan