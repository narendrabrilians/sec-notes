# HTTP (Hypertext Transfer Protocol)

**HTTP** adalah protokol komunikasi berbasis teks yang digunakan untuk mentransfer data antara **client** (biasanya browser) dan **server**.

### Client-Server Model

HTTP bekerja berdasarkan model *request-response*, di mana **client mengirim request** dan **server merespons**.

### Stateless

HTTP bersifat **stateless**, artinya:

> Setiap HTTP request adalah **independen**, tidak ada hubungan antar request.

### HTTP Versions

🔗 [`MDN Web Docs - HTTP Versions`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Evolution_of_HTTP)

## 🔒 HTTPS

**HTTPS** = HTTP + SSL/TLS (enkripsi)

- Tujuan: Mengamankan data yang dikirimkan.

- Data dalam HTTP (plaintext) bisa dilihat oleh siapa pun di jaringan.

- HTTPS mengenkripsi **request** dan **response**, lebih aman.

## 🔄 HTTP Request & Response Format

Struktur dasar:

```
Start Line
Headers
(blank line)
Body (opsional)
```

### Contoh HTTP Request

```
GET /kebaikan.html HTTP/1.1
Host: www.narendrakebaikan.com
User-Agent: Mozilla/5.0
```

### Contoh HTTP Response

```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1024

<html>...</html>
```

## 📬 HTTP Methods

| Method  | Deskripsi Singkat |
|---------|-------------------|
| **GET**     | Digunakan untuk melakukan request data |
| **HEAD**    | Sama seperti dengan GET, tapi tanpa membutuhkan response body |
| **POST**    | Mengirim data ke server (buat data baru) |
| **PUT**     | Untuk mengganti semua data yang terdapat di Server dengan data baru yang dikirim di request |
| **DELETE**  | Menghapus data |
| **PATCH**   | Mengubah sebagian data |
| **OPTIONS** | Digunakan untuk mendeskripsikan opsi komunikasi yang tersedia |
| **TRACE**   | Debugging, mencerminkan request kembali ke client |

## 🌍 URL (Uniform Resource Locator)

Contoh:

```
http://www.narendrakebaikan.com:80/path/to/file.html?key1=value1&key2=value2#kebaikan
```

Anatomi:

- **Scheme**: `http`

- **Authority**: `www.narendrakebaikan.com:80`

- **Path**: `/path/to/file.html`

- **Query**: `?key1=value1&key2=value2`

- **Anchor**: `#kebaikan`

[`What is a URL`](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/What_is_a_URL)

![URL Anatomy](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/What_is_a_URL/mdn-url-all.png)

## 📦 HTTP Header

Header memberikan informasi tambahan di Request / Response.

Contoh:

```
Content-Type: application/json
Authorization: Bearer <token>
User-Agent: Mozilla/5.0
```

Contoh:

- Tentukan format body (`Content-Type`)

- Kirim token autentikasi (`Authorization`)

- Identifikasi client (`User-Agent`)

## ✅ HTTP Status Codes

| Range | Keterangan          |
|-------|----------------------|
| 1xx   | Informational        |
| 2xx   | Success (misal: `200 OK`) |
| 3xx   | Redirect (misal: `301 Moved Permanently`) |
| 4xx   | Client Error (misal: `404 Not Found`) |
| 5xx   | Server Error (misal: `500 Internal Server Error`) |

## 📄 HTTP Body

Body adalah bagian opsional yang memuat data sebenarnya (biasanya dalam POST, PUT, dll).

Contoh:

- JSON

- XML

- Form-encoded

- Binary file (image, video, dll)

## 🔁 Redirect

Redirect terjadi saat server memberitahu browser untuk **pindah ke URL lain**.

Contoh:
```
HTTP/1.1 302 Found
Location: https://narendrakebaikan.com/kebaikan-page
```

## 🍪 HTTP Cookies

### Cookie dari Server ➡️ Client

Header:

```
Set-Cookie: user=narendra
Set-Cookie: session=kebaikan
```

### Cookie dari Client ➡️ Server

Browser akan mengirim kembali cookie di request berikut:

```
Cookie: user=narendra; session=kebaikan
```

> Cookie sering digunakan untuk **session login**, tracking user, dll.

## ♻️ HTTP Caching

Caching = menyimpan data response di client (sementara), agar tidak perlu request ulang.

Sangat cocok untuk:

- Gambar

- Video

- CSS / JS

- File statis

### Cache-Control (Response Header)

```
Cache-Control: max-age=86400
```

> Artinya: simpan cache selama 1 hari (86400 detik)

## 🔍 Sumber
[`Programmer Zaman Now - HTTP`](https://docs.google.com/presentation/d/13RSfJzqjnvdUO33u2K1m8vefa7sn9rIZ5h4wUa-DIqk/edit?slide=id.p#slide=id.p)  


## 📚 Belajar

[MDN Web Docs – Overview of HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview)
