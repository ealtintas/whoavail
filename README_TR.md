## README_TR.md

# whoavail

WHOIS sorgusu yaparak alan adı uygunluğunu kontrol eden basit bir Bash betiği.

---

## Özellikler

- Bir veya daha fazla alan adını kontrol eder.
- Alan adı listesini bir dosyadan okuma desteği.
- WHOIS çıktısını zaman damgalı dosyalara kaydeder.
- WHOIS çıktısındaki "uygun" mesajlarını sezgisel olarak tespit eder.
- Rate-limit riskini azaltmak için sorgular arasında bekleme yapar.

---

## Kullanım

```bash
whoavail domain1.com domain2.net
whoavail filename.lst
whoavail abcdfg.{com,net,org}
whoavail domain{1,2,3}.com
whoavail {abcd,efgh,jklm}.{com,net,org}
whoavail {a..z}domain.{com,net,org} | tee -a domainavail.lst
whoavail {a..z}{a..z}{a..z}.{com,net,org} | tee -a domainavail.lst
````

* **İlk parametre** bir dosya adıysa (ör. `filename.lst`), dosyadaki her satır bir alan adı olarak işlenir ve kontrol edilir.

---

## Örnek

```bash
whoavail example.com
```

Örnek çıktı:

```
240704-103015	Available	example.com
```

## Gereksinimler

* Bash
* whois komut satırı aracı

---

## Notlar

* Betik her WHOIS çıktısını mevcut dizinde zaman damgalı bir dosyaya kaydeder.
* WHOIS sunucuları aşırı sorguları sınırlayabilir. Betik sorgular arasında 3 saniye bekler.

