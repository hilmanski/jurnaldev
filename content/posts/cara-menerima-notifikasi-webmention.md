---
title: "Cara Menerima Notifikasi Webmention"
date: 2021-09-18T00:00:00
description: "Bagaimana cara menerima notifikasi webmention untuk memberitahu sebuah URL sudah menulis tentang url kamu di websitenya"
tags: ["webmention"]
series: ["Eksplorasi teknologi Webmention"]
draft: true
---

Sebelumnya saya menulis seputar [webmention di sini](https://jurnal.dev/webmention). Sekarang kita masuk ke bagian teknikal cara menerimanya.

Kalau kamu ingin mengimplementasikan, coba cari cara yang lebih mudah, dibanding memulainya dari nol. Contoh "wordpress plugin webmention" atau "webmention for ruby on rails" dll. sesuai tool atau teknologi yang kamu gunakan.

Bagian ini adalah proses teknikal bagaimana menerima webmention. Sekedar pengetahuan di balik layar atau untuk kamu yang ingin mengimplementasikannya sendiri.

## Verifikasi
Karena saat [mengirim webmention](https://jurnal.dev/cara-mengirim-notifikasi-webmention/) kita menyertakan parameter `source` dan `target`, karena itu kita harus menerima dan verifikasi kedua parameter ini.

1. Uji bahwa keduanya adalah valid URL
2. source dan Target tidak boleh sama

VErifikasi harus berjalan asynchronous untuk mencegah serangan DoS(Denial of Service).

## Respon menerima webmention
Nilai yang direturn adalah `HTTP 201 Created` dan Location header dari URLnya

contoh:
```
HTTP/1.1 201 Created
Location: http://aaronpk.example/webmention/DEhB9Jme
```

atau jika tanpa URL, return `HTTP 202 Accepted`




## Refrensi
[https://www.w3.org/TR/webmention/#receiving-webmentions](https://www.w3.org/TR/webmention/#receiving-webmentions)