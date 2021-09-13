---
title: "Apa itu Webmention"
slug: webmention
date: 2021-09-13T16:01:59+08:00
description: "Berkenalan apa itu webmention, teknologi untuk memberitahu URL lain saat kamu memention url tersebut. Sebaliknya kamu bisa menerima notifikasi saat dimention"
tags: ["catatan"]
series: ["Eksplorasi teknologi Webmention"]
---

Saya sering mendengar kata "mention" dari twitter. Ketika seseorang ingin menyebutkan orang lain ia akan "mention" akun lain tersebut. Webmention tidak jauh berbeda, tapi ini bukan antar akun twitter, melainkan antar URL website.

## Mengenal webmention

Webmention adalah cara sederhana untuk mengirim notifikasi ke sebuah URL yang kamu sebutkan (mention) di websitemu. Dari perspektif penerima, webmention berarti kamu menyiapkan notifikasi saat ada orang lain yang menyebutkan website kamu.

Teknologi ini bisa dimanfaatkan untuk membuat website menjadi lebih 'sosial', dengan menjadikannya sebagai sistem komentar, like atau respon secara umum tanpa perlu pihak ketiga.

## Contoh
1 Saya posting hal menarik di blog ini (ceritanya saya sudah implementasi webmention untuk menerima notifikasi).  
2. Kamu ingin menanggapi konten saya di artikelmu, kamu pun membuat postingan sendiri di blog/websitemu dan menyebutkan website(url artikel saya) di sana.  
3. Dengan webmention, website kamu akan mengirim notifikasi ke server saya bahwa artikel X sudah di-mention  
4. Website saya menverifikasi "oh benar", saya di mention di website kamu, saya pun menambahkan informasi tersebut di artikel X saya.

## Syarat
Dibutuhkan kedua website untuk mengimplementasikan teknologi webmention (mengirim dan menerima) agar bisa berjalan.

Aritkel [cara mengirim notifikasi webmention](https://jurnal.dev/cara-mengirim-notifikasi-webmention/)  
Aritkel cara menerima notifikasi webmention (coming soon)


## Menguji webmention
Kamu bisa mengujinya di [webmention rocks](https://webmention.rocks/)  
Ini adalah website untuk menvalidasi implementasi kamu.

## Informasi lain
- Webmention adalah rekomendasi dari W3C (World Wide Web Consortium) untuk menggantikan pingback, yang hanya menggunakan HTTP dan x-www-form-urlencoded.

- Webmention merupakan salah satu pilar penting dari [indieweb](https://jurnal.dev/indieweb/)

## Pendapat saya
Webmention bisa menjadi alternatif untuk orang-orang yang tidak ingin menggunakan "perusahaan" atau layanan lain di websitenya seperti disqus, sebagai layanan menampung komentar misalnya.

Tentu saja jalannya masih panjang, bisa dilihat dari sulitnya mengimplementasikan sistem webmention di website kita. Untuk penggunanya pun bisa saya katakan masih terisolasi untuk kalangan "indie developer". Untuk teman-teman yang punya blog dengan pembaca umum, tentunya tidak saya sarankan menggunakan ini, karena akan mempersulitkan sistem komentarnya.

Masih perlu banyak orang yang menggaungkan seputar webmention agar orang-orang lebih familiar dan perlu banyak kemudahan yang ditawarkan untuk mengimplementasikannya dalam bentuk open source atau layanan gratis. 

Karena jika yang membuat layanannya adalah perusahaan berbayar, sulit untuk mempertemukan ideologi dari "indieweb" dengan layanan lain, yang ingin menghilangkan ketergantungan dari pihak ketiga.

## Refrensi
[Your first Webmention](https://aaronparecki.com/2018/06/30/11/your-first-webmention#responses)  
[Layanan hosting untuk webmention](https://webmention.io/)  
[Webmention IndieWeb](https://indieweb.org/Webmention)  
[Webmention w3org](https://www.w3.org/TR/webmention/#authorsnote-p-2)

