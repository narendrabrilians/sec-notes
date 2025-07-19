# Nmap

**Nmap** (Network Mapper) adalah tool open-source yang digunakan untuk scanning jaringan, menemukan host, layanan, port terbuka, dan informasi sistem lainnya.

## 📄 Perintah Dasar & Help

```bash
man nmap

nmap --help

nmap <target>
```

Secara default, Nmap hanya memindai **1000 port umum**.

```bash
nmap 192.168.1.1/24
```

Melakukan scan terhadap satu subnet/range IP.

## 🔍 Jenis Scanning

### TCP SYN Scan (Stealth Scan)

```bash
nmap -sS <target>
```

- Mengirimkan **SYN** (permintaan koneksi).

- Jika menerima **SYN-ACK**, maka port **open**.

- Jika menerima **RST**, maka port **closed**.

- Jika tidak ada balasan, maka port **filtered** (tidak bisa ditentukan).

> Disebut *stealth* karena tidak menyelesaikan full TCP handshake.

### TCP Connect Scan

```bash
nmap -sT <target>
```

- Melakukan **full TCP connection**.

- Meninggalkan jejak lebih banyak di log target.

### UDP Scan

```bash
nmap -sU <target>
```

- Digunakan untuk mendeteksi layanan berbasis UDP.

- Responnya tidak selalu jelas, membuat scan **lebih lambat dan ambigu**.

## ⚙️ OS & Service Detection

### Menebak OS

```bash
nmap -O <target>
```

### Mengetahui Versi Layanan

```bash
nmap -sV <target>

nmap -sV --version-intensity <0-9> <target>
```

### Aggressive Scan

```bash
nmap -A <target>
```

Menggabungkan: OS detection, version detection, default script scanning (NSE), dan traceroute.

## 🎯 Filtering & Output

```bash
nmap -sn <target-range>      # Host discovery (tanpa scan port)

nmap -p 80 <target>          # Scan port 80

nmap -p 80,22,443 <target>   # Scan beberapa port spesifik

nmap -p 1-65535 <target>     # Scan seluruh port
```

### Output ke File

```bash
nmap -sS <target> >> output.txt

nmap -oN output.txt -sS <target>
```

## 🕵️‍♂️ Evasion & Bypass Firewall/IDS

### Fragmenting Packets

```bash
nmap -f <target>
```

- Memecah header TCP/IP menjadi potongan kecil.
- **Tujuan**: Menghindari deteksi firewall/IDS.

### Decoy Scan

```bash
nmap -D <decoy1>,<decoy2>,<decoy3>,<target>

nmap -D RND:10 <target>
```

- Menambahkan IP **decoy** agar IDS/IPS kesulitan mengidentifikasi scanner sebenarnya.

### IP Spoofing + Interface

```bash
nmap -S <ip-palsu> -Pn -e eth0 -g <source-port>
```

- **-S**: Memalsukan IP sumber.

- **-e**: Pilih interface.

- **-g**: Pilih source port (misal: 53, 80 untuk menyamar jadi DNS/HTTP).

- **-Pn**: Lewati host discovery (anggap host selalu up).

📝 **Catatan**:

- Gunakan opsi dengan hati-hati di lingkungan produksi atau tanpa izin.

- Untuk evasion atau fragmenting, efektivitas tergantung konfigurasi firewall/IDS target.

## 📚 Belajar

[`nmap.org/`](https://nmap.org/)