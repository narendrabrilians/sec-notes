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

- **Port Scanning**: Menemukan port terbuka (misalnya: `nmap`)  

- **Service Detection**: Mengidentifikasi layanan di balik port  

- **Vulnerability Scanning**: Mendeteksi kerentanan (misalnya: `Nessus`, `OpenVAS`)

## 🎯 Exploitation & Gaining Access

Menyerang target dengan memanfaatkan celah keamanan untuk memperoleh akses tidak sah.

### Contoh serangan:

- SQL Injection  

- XSS  

- RCE  

- Brute Force

### Tools:

- `Metasploit`, `SQLmap`, `Burp Suite`, `Hydra`, custom script

## 🧪 Post-Exploitation

Tahap setelah berhasil mendapatkan akses ke sistem target. Fokus pada menjaga akses, melakukan eksplorasi lanjutan, dan menghapus jejak untuk menghindari deteksi.

### Contoh kegiatan:

- **Privilege Escalation**: Meningkatkan hak akses dari user biasa menjadi admin/root  

- **Maintaining Access**: Menjaga agar akses tetap tersedia (misalnya: backdoor, SSH key, cronjob)  

- **Covering Tracks**: Menghapus jejak aktivitas agar tidak terdeteksi (misalnya: hapus log, rootkit)


## 📝 Reporting

Tahap akhir yang berfokus pada dokumentasi seluruh proses pengujian, temuan celah keamanan, dan rekomendasi perbaikan.

**Isi laporan biasanya mencakup:**

- Ringkasan eksekutif

- Detail kerentanan yang ditemukan

- Bukti eksploitasi (screenshots, log, PoC)

- Dampak dan tingkat risiko

- Rekomendasi mitigasi