---
title: "Webmention [Masih Draft]"
slug: webmention
date: 2021-09-13T16:01:59+08:00
description: "Berkenalan apa itu webmention, teknologi untuk memberitahu URL lain saat kamu memention url tersebut. Sebaliknya kamu bisa menerima notifikasi saat dimention"
tags: ["catatan"]
---
Webmention adalah cara sederhana untuk memberitahu URL yang kamu sebutkan (mention) di websitemu. Dari perspektif penerima, webmention berarti kamu menyiapkan notifikasi saat ada orang lain yang menyebutkan website kamu.

Teknologi ini bisa dimanfaatkan untuk membuat website menjadi lebih 'sosial', dengan menjadikannya sebagai sistem komentar, like atau respon secara umum tanpa perlu pihak ketiga.

## Contoh
1 Saya posting hal menarik di blog ini (ceritanya saya sudah implementasi webmention untuk menerima notifikasi).  
2. Kamu ingin menanggapi konten saya di artikelmu, kamu pun membuat postingan sendiri di blog/websitemu dan menyebutkan website(url artikel saya) di sana.  
3. Dengan webmention, website kamu akan mengirim notifikasi ke server saya bahwa artikel X sudah di-mention  
4. Website saya menverifikasi "oh benar", saya di mention di website kamu, saya pun menambahkan informasi tersebut di artikel X saya.

## Syarat
Dibutuhkan kedua website untuk mengimplementasikan teknologi webmention (mengirim dan menerima) agar bisa berjalan.

## Protokol Webmention

Bagian ini adalah proses teknikal bagaimana webmention berkerja.

### 1. Mention target
Sebuah halaman (bisa blog atau konten apapun) menyebutkan dan memberi link ke halaman lain. Bisa dengan tag a link HTML biasa.
contoh di jurnal.dev salah satu halamannya berisi: 
```
<!doctype html>
<html>
  <body>
  	Saya suka membaca <a href="https://hilman.space/tulisan">Tulisan Hilman</a>
  </body>
</html>
```
* Di sini website hilman.space kita sebut sebagai "target"

### 2. Pengirim menguji halaman target
Pengirim harus membuka URL target dan mencari HTTP link header dengan nilai `rel=webmention`. Jika halaman target adalah HTML maka yang dicari adalah tag `<link>` atau `<a>`.


## Menguji webmention
Kamu bisa mengujinya di [webmention rocks](https://webmention.rocks/)  
Ini adalah website untuk menvalidasi implementasi kamu.

## Fun Fact
- Webmention adalah rekomendasi dari W3C (World Wide Web Consortium) untuk menggantikan pingback, yang hanya menggunakan HTTP dan x-www-form-urlencoded.

- Webmention merupakan salah satu pilar penting dari [indieweb](https://jurnal.dev/indieweb/)

## Refrensi
[Layanan hosting untuk webmention](https://webmention.io/)  
[Webmention IndieWeb](https://indieweb.org/Webmention)  
[Webmention w3org](https://www.w3.org/TR/webmention/#authorsnote-p-2)

