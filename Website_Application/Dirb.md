## Dirb

**Dirb** adalah *web content scanner* yang digunakan untuk mencari file atau direktori tersembunyi di dalam sebuah web server.

## 🔧 Syntax

```bash
dirb <url_base> [<wordlist_file>] [options]
```

- `<url_base>`: URL target, misal `http://target.com/`

- `<wordlist_file>` *(opsional)*: Path ke file wordlist yang ingin digunakan (jika tidak ditentukan, Dirb akan menggunakan wordlist default-nya)

- `[options]`: Tambahan opsi seperti ekstensi, SSL, dll

## 📘 Contoh Penggunaan

### Scan Direktori Dasar

```bash
dirb http://target.com/
```

### Scan dengan Ekstensi Tertentu
Menambahkan ekstensi `.html` ke setiap word di wordlist:

```bash
dirb http://target.com/ -X .html
```

### Pakai Wordlist (contoh: apache.txt)

```bash
dirb http://target.com/ /usr/share/dirb/wordlists/vulns/apache.txt
```

### Scan Website HTTPS (SSL)

```bash
dirb https://secure-target.com/
```

## 📚 Belajar

[www.kali.org/tools/dirb/](https://www.kali.org/tools/dirb/)
