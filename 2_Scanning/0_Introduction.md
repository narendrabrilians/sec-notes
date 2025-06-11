# 🔍 SCANNING

**Scanning** adalah proses dalam penetration testing yang melibatkan pengiriman packet langsung ke sistem target, dengan tujuan menganalisis respons yang diberikan. Dari respons tersebut, attacker atau security analyst dapat mengidentifikasi:

- Port yang terbuka

- Layanan yang berjalan

- Versi software

- Potensi kerentanan

## 📦 Jenis Packet yang Digunakan

Selama proses scanning, jenis packet yang umum digunakan antara lain:

1. **TCP packets**

2. **UDP packets**

3. **ICMP packets**

## 🔁 TCP

TCP (Transmission Control Protocol) adalah protokol berbasis koneksi yang menggunakan mekanisme **Three-Way Handshake** untuk memulai komunikasi.

**Three-Way Handshake:**

1. **SYN** – Klien mengirim request koneksi.

2. **SYN-ACK** – Server merespons request dari klien.

3. **ACK** – Klien mengonfirmasi dan koneksi terbentuk.

Scanning berbasis TCP (misalnya dengan `nmap`) sering digunakan untuk mendeteksi:

- Port Open (Terbuka)

- Port Closed (Tertutup)

- Port Filtered (Tools belum bisa memastikan port open atau closed)

## 📡 UDP

UDP (User Datagram Protocol) adalah protokol tanpa koneksi yang tidak menggunakan mekanisme handshake.

Karena tidak ada konfirmasi koneksi:

- Respon biasanya hanya diterima jika port **terbuka dan aplikasi merespons**.

- Jika **tidak ada respons**, bisa jadi port terbuka, tertutup, atau difilter, ini membuat scanning UDP **lebih lambat dan ambigu**.

**UDP scanning** bermanfaat untuk mendeteksi layanan seperti:

- DNS (port 53)

- SNMP (port 161)

- TFTP (port 69)

