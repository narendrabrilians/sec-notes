# Netdiscover

**Netdiscover** adalah tool berbasis ARP (Address Resolution Protocol) yang digunakan untuk menemukan perangkat (devices) yang terhubung ke jaringan lokal (LAN).

## 🔧 Apa Itu ARP Tool?

ARP (Address Resolution Protocol) digunakan untuk memetakan alamat IP ke alamat MAC di dalam jaringan lokal. **ARP Tools** seperti `netdiscover` atau `arp-scan` memanfaatkan protokol ini untuk:

- Menemukan perangkat aktif dalam satu segmen jaringan

- Mengidentifikasi vendor dari MAC address

- Mengirim paket ARP broadcast untuk menemukan perangkat, tanpa probing layanan seperti HTTP, SSH, dll.

## 💻 Perintah Dasar

```bash
sudo netdiscover
```

Netdiscover akan menampilkan informasi seperti:

- IP Address

- MAC Address

- Vendor perangkat (Jika dikenali)

## 🔍 ARP help

```bash
sudo arp --help
```

> Perintah ini menunjukkan opsi untuk melihat dan memanipulasi ARP table di sistem lokal. Tidak secara langsung terkait dengan netdiscover, tapi masih dalam konteks ARP.

## 📚 Belajar

[`www.kali.org/tools/netdiscover/`](https://www.kali.org/tools/netdiscover/)

[`github.com/netdiscover-scanner/netdiscover`](https://github.com/netdiscover-scanner/netdiscover)