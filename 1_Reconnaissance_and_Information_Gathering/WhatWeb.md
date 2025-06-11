# WhatWeb

**WhatWeb** adalah alat yang berguna untuk mengidentifikasi teknologi web yang digunakan oleh suatu situs atau server.

## ⚙️ Mode Operasi

WhatWeb memiliki dua mode utama yang memengaruhi cara kerjanya:

### Stealthy Mode

- **Tujuan**: Menghindari deteksi oleh sistem target.

- **Risiko Deteksi**: Rendah, karena interaksinya minimal.

- **Jumlah Request**: Mengirim sedikit request ke target.

### Aggressive Mode

- **Tujuan**: Mengumpulkan informasi lebih mendalam tentang teknologi web yang digunakan.

- **Risiko Deteksi**: Tinggi, karena interaksinya lebih intens.

- **Jumlah Request**: Mengirim banyak request ke target.

## 💻 Penggunaan Dasar

Berikut adalah beberapa contoh penggunaan perintah WhatWeb:

### Help

```bash
whatweb --help
```

### Memindai Domain

```bash
whatweb <domain>
```

### Memindai Domain dengan Output Verbose

```bash
whatweb <domain> -v
```

### Memindai Banyak Target

```bash
whatweb target1.com target2.com
```

> Kita juga bisa menggunakan rentang IP atau file yang berisi daftar target.
> Cek bantuan `whatweb --help` untuk format lengkap.

## 🚀 Contoh Penggunaan Lanjutan

### Memindai Rentang IP dengan Tingkat Agresi Maksimal dan Output Verbose

```bash
whatweb 192.168.1.0-192.168.1.255 --aggression 3 -v
```

### Memindai Rentang IP dengan Agresi Tinggi, Output Verbose, dan Tanpa Error Message

```bash
whatweb 192.168.1.0-192.168.1.255 --aggression 3 -v --no-error
```

## 📝 Logging Hasil Pemindaian

Hasil pemindaian WhatWeb dapat disimpan ke dalam file untuk dianalisis lebih lanjut.

### Simpan Hasil ke File

```bash
whatweb 192.168.1.0-192.168.1.255 --aggression 3 -v --no-error --log-verbose=results.txt
```

## 📚 Belajar

[`www.kali.org/tools/whatweb/`](https://www.kali.org/tools/whatweb/)

[`github.com/urbanadventurer/WhatWeb`](https://github.com/urbanadventurer/WhatWeb)