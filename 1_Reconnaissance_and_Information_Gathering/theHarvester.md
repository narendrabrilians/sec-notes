# theHarvester

**theHarvester** adalah alat open-source untuk pengumpulan informasi (OSINT) yang digunakan untuk mencari email, subdomain, nama host, dan data lainnya dari berbagai sumber publik.

## ⚙️ Fungsi Utama

theHarvester berguna dalam fase reconnaissance (pengintaian) saat melakukan pengujian keamanan atau pengumpulan informasi target secara pasif.

## 💻 Penggunaan Dasar

Beberapa contoh penggunaan umum perintah `theHarvester`:

### Help

```bash
theHarvester --help
```

### Memindai Domain Menggunakan Semua Sumber yang Tersedia

```bash
theHarvester -d <domain> -b all
```

Contoh:

```bash
theHarvester -d example.com -b all
```

### Memindai Domain Hanya dari Google

```bash
theHarvester -d <domain> -b google
```

Contoh:

```bash
theHarvester -d example.com -b google
```

---

## 📚 Belajar

[`github.com/laramies/theHarvester`](https://github.com/laramies/theHarvester)  

[`www.kali.org/tools/theharvester/`](https://www.kali.org/tools/theharvester/)
