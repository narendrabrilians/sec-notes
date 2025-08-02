# Broken Authentication

**Broken Authentication** adalah kondisi ketika aplikasi **gagal secara aman memverifikasi identitas pengguna**,  
sehingga memungkinkan attacker untuk:

- Login sebagai user lain tanpa kredensial yang sah

- Menyamar sebagai pengguna yang sah (session hijacking)

- Mengeksploitasi kelemahan sistem otentikasi (misalnya login tanpa password, predictable session ID, brute force)


## 🔐 Session

Session adalah **mekanisme penyimpanan status login** antara client dan server.  
Biasanya server menyimpan session ID dan mengirimkannya ke client sebagai cookie.

Contoh:  
Setelah login, server mengirimkan cookie `sessionid=abc123` ke browser.  
Browser akan mengirimkan kembali cookie ini pada setiap request.

## 🔒 Session Management

Mengelola session dengan aman meliputi:

- Pembuatan session ID yang acak dan tidak dapat ditebak

- Session timeout (expired otomatis)

- Logout yang benar-benar menghapus session

- Penggunaan HTTPS untuk mencegah pencurian session

## 🎯 Session Hijacking

Menyerang session dengan cara **mencuri session ID**, biasanya lewat:

- Sniffing (kalau tanpa HTTPS)

- XSS (mencuri cookie)

- CSRF (menyalahgunakan session aktif)

## 🧷 Session Fixation

Menyerang dengan cara **memaksa korban menggunakan session ID yang sudah diketahui attacker.**

Contoh alur:

1. Attacker membuat session ID: `sessionid=known123`

2. Attacker membuat link ke target web dengan ID itu

3. Jika korban login tanpa session di-reset, attacker bisa pakai ID yang sama untuk ambil alih session

## 🔐 Weak Encryption / Weak Session Cookies

- Session ID mudah ditebak (misal: angka urut)
- Session cookie tidak diberi flag `HttpOnly`, `Secure`, atau `SameSite`
- Tanpa HTTPS, cookie bisa dicuri

## 🧪 Studi Kasus

### Nama user: `kebaikan`  
Jika attacker bisa register dengan nama: `" kebaikan"` (ada spasi di awal), dan saat login menggunakan `" kebaikan"`, ternyata **diperlakukan sebagai `kebaikan`**, itu artinya aplikasi gagal membedakan nama yang valid, termasuk Broken Authentication.

## 🍪 Bisa Pakai Cookie

Jika cookie menyimpan data penting seperti:

```
username=kebaikan; id=1001
```

Attacker bisa coba ubah nilainya lewat browser developer tools, lalu reload aplikasi untuk lihat efeknya.

## 🔑 Basic Authorization

- Mekanisme otentikasi dasar via header HTTP

- Format:

    ```
    Authorization: Basic <base64>
    ```

- Biasanya berisi Base64 dari `username:password`

    Contoh:

    ```
    Authorization: Basic a2ViYWlrYW46MTIzNDU=
    ```

    Decode:

    ```
    kebaikan:12345
    ```

Jika password disimpan dengan encoding lemah (base64 bukan encryption), maka mudah ditebak/dicuri.

## 📌 Ringkasan

Broken Authentication terjadi ketika aplikasi gagal:

- Mengelola session dengan aman

- Melindungi credential (username/password)

- Membedakan identitas pengguna secara unik

## 📚 Belajar

[OWASP A2:2017-Broken Authentication](https://owasp.org/www-project-top-ten/2017/A2_2017-Broken_Authentication)
