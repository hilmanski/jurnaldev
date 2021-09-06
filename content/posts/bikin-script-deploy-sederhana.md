---
title: "Bikin Script Deploy Sederhana"
description: "Sebelum push kode, kamu perlu menjalankan beberapa script? seperti git pull, lalu git add, git commit, bla bla bla.. coba kita bikin otomatis yuk"
date: 2020-11-27T07:04:25+08:00
featured_image: https://i.ibb.co/CwM3Q7F/pp.jpg
slug: script-deploy
tags: ["deployment", "tips"]
---

Kalau kamu sudah berpindah dari menggunakan FTP jadi menggunakan deployment berbasis Git, kamu mungkin sering melakukan ini:
```
git add .
git commit -m "pesan commit"
git push origin namaBranch
```
Saya melakukan ini setiap kali ingin melakukan perubahan, kelihatannya bukan masalah, tapi cukup mengganggu kalau harus selalu melakukannya karena ada 3 langkah yang perlu dibuat.

Prinsip programmer pada umumnya, DRY (Don't repeat yourself). Membuat skrip sederhana untuk memangkasnya:

Pertama, Bikin file bernama deploy.sh di proyek kamu

Selanjutnya, isi file ini dengan script yang ingin dibuat otomatis, pada kasus ini:

```
git add .
git commit -m "pesan commit"
git push origin main
```
    
*Master contoh branch yang kamu push.

Tapi tunggu dulu, pesan commit kita masih statis, kamu bisa buat menjadi dinamis dengan:

```
git add .

msg="update site `date`"
if [ $# -eq 1 ]
    then msg="$1"
fi

git commit -m "$msg"

git push origin master
```
    
Di atas kita membuat variable bernama "msg", dengan nilai default tanggal hari ini dan text update site, tapi jika user memberikan tambahan parameter makan akan mengganti nilai "msg" tersebut.

Kamu juga bisa menyesuaikan, misalnya ingin pull terlebih dahulu, tinggal tambahkan git pull di awal baris.

Sekarang kamu bisa coba menjalankan script ini dengan:

```
./depoy.sh "script otomatis berjalan!"
```
    