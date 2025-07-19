# 🕵️ INFORMATION GATHERING & RECONNAISSANCE

Tahap awal dalam penetration testing yang bertujuan untuk mengumpulkan informasi sebanyak mungkin tentang target, baik secara pasif maupun aktif.

## 🔍 Passive Reconnaissance

Pengumpulan informasi **tanpa interaksi langsung** dengan sistem target.

- Informasi diperoleh dari sumber publik
- Risiko terdeteksi rendah
- Cocok untuk pengumpulan awal

### Contoh aktivitas:
- Menelusuri website dan subdomain
- Google Dorking
- Whois lookup
- Melihat metadata dokumen publik
- Analisis DNS publik
- Melihat media sosial publik

### Contoh tools:
- `whois`
- `theHarvester`
- `Shodan`
- `Google`

## ⚡ Active Reconnaissance

Pengumpulan informasi melalui **interaksi langsung** dengan sistem target.

- Bisa menimbulkan traffic atau alert
- Berisiko lebih tinggi untuk terdeteksi
- Cocok saat pengujian sudah mulai dilakukan

### Contoh aktivitas:
- Port scanning
- Service enumeration
- Vulnerability scanning
- Ping sweep
- Subdomain brute-force

### Contoh tools:
- `nmap`
- `masscan`
- `nikto`
- `whatweb`
- `dnsenum`