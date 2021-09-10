---
title: "Membuat static site generator"
date: 2021-09-06T15:05:13+08:00
description: "Saya mau bercerita tentang pengalaman membuat static site generator sendiri, yang diberi nama Mini SSG"
slug: minissg
tags: ["ssg","bikinbikin"]
featured_image: https://i.ibb.co/rbTBp5W/Screen-Shot-2021-07-08-at-10-27-49-AM.png
---
Saya mau bercerita tentang pengalaman membuat static site generator sendiri, yang diberi nama [Mini SSG](https://minissg.vercel.app/)

## Latar belakang
Karena hobi sering membuat website, saya cukup terganggu ketika harus membuat sesuatu dari nol. Tentu saya bukan orang pertama yang mengalami hal ini, karena alasan itulah banyak tool, framework dan bantuan lainnya yang bertebaran.

Spesifiknya masalah saya ketika hanya butuh beberapa halaman, (bukan seperti blog), di mana saya harus menulis header, SEO, footer, konten dan lain-lain. Kurang lebih untuk website personal, perusahaan atau website marketing statis.

## Masalah (saya) dengan SSG sekarang
Ada banyak SSG(static site generator). Tapi saya merasa spesifik untuk jenis website yang saya buat belum ada atau overkill. Karena sebagian besar SSG dibuat dengan bayangan akan menjadi blog atau sebuah konten dinamis, alhasil banyak fitur yang saya tidak butuhkan. Karena itulah terpikirkan membuat sesuatu yang sederhana dan saya sendiri suka.

## Mulai dari akhir
Saya salut dengan Taylor Otwell, pendiri Laravel, ia berhasil membuat PHP yang sering mendapat komentar negatif, kembali naik citranya. Lewat laravel, ia membuat berbagi syntax yang sangat nyaman dipakai dan intuitif, sehingga mudah diingat.

Filosofi ini yang ingin saya gunakan di Mini SSG, saya mulai dari akhir.

Saya membayangkan, kalau saya mau import sesuatu, kira-kira seperti apa?
```
@import(namafile)
```
Yap.. semudah itu! teman-teman bisa melihat syntax aslinya di [website mini ssg](https://minissg.vercel.app/tour)

Bayangan lain.. kira kira kalau saya mau menggunakan sebuat layout, seperti apa..
```
@layout(base) 
```
Yes, lagi lagi sesimpel itu!

Sebelum membayangkan rumitnya membuat ini, saya sudah merencanakan seperti apa saya ingin menggunakannya nanti.

Sebelumnya saya sering terbalik, karena sudah terlanjur ribet membuatnya, akhirnya melupakan sisi kenyamanan menggunakan tool tersebut.

## Memilih tool
Saya mencoba riset seperti apa jika ingin membuat dengan Go (karena terkenal dengan kecepatan). Saya menemukan harus mengintegrasikan dengan homebrew nanti untuk install seperti Hugo. Batallah niatnya, saya harus memikirkan apa yang orang banyak familiar (paling tidak di mata saya).

Jatuhlah pilihan ke bahasa seribu ummat, Javascript, Nodejs.

Saya mulai mencari artikel bagaimana membuat website statis sederhana, hingga jadi seperti ini.

## Masalah di perjalanan

### Regex
Tantangan terbesar adalah karena mini ssg adalah sebuah 'build tool', yang perlu membaca syntax buatan sendiri, saya harus sangat berhati-hati mengimplementasikan reg-ex. regular expression. Katanya sih 9 dari 10 programmer, ngga suka regex (:P)

### Membatasi fitur
Semakin lama, semakin banyak rasanya ingin menambahkan fitur. Tapi harus hati-hati saya bisa berakhir dengan tool ssg yang lain, karena itu perlu belajar, mengingat apa tujuan awal tool ini. Lebih baik selesaikan masalah tersebut dengan baik.

### Live Reload
Cukup lama saya menghabiskan waktu untuk mengimplementasikan fitur live reload. Ketika seseorang merubah sesuatu di filenya, maka program mini ssg harus dijalankan ulang dan mereload browser. 

## Gunakan sendiri
Selama membuat website mini-ssg sendiri, saya menggunakan tool ini, agar bisa merasakan langsung. Alhasil banyak yang kurang! mulai dari bug, fitur atau sedikit bumbu DX(developer experience) yang bisa dibenahi. Semuanya bisa diketahui, karena saya sendiri menggunakannya.

## Status saat ini (6 Sept 2021)
Status sudah terpublish kurang lebih 1 bulan.
Lihat status install di [NPM](https://www.npmjs.com/package/mini-ssg).

Saya senang karena sudah belajar membuat sesuatu yang saya butuhkan.
Sudah beberapa kali saya menggunakannya, termasuk website mini ssg sendiri.

Kalau bisa mengulang waktu, apakah saya akan membuat ini lagi? Iya!
Dalam kata lain, tidak menyesal :)