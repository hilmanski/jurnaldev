---
title: "Cara Mengirim Notifikasi Webmention"
date: 2021-09-13T19:43:54+08:00
description: "Bagaimana cara mengirim notifikasi webmention untuk memberitahu sebuah URL sudah dimention di link lain?"
tags: ["catatan"]
series: ["Eksplorasi teknologi Webmention"]
---

Sebelumnya saya menulis seputar [webmention di sini](https://jurnal.dev/webmention). Sekarang kita masuk ke bagian teknikal cara mengirimnya.

Kalau kamu ingin mengimplementasikan, coba cari cara yang lebih mudah, dibanding memulainya dari nol. Contoh "wordpress plugin webmention" atau "webmention for ruby on rails" dll. sesuai tool atau teknologi yang kamu gunakan.

Bagian ini adalah proses teknikal bagaimana webmention berkerja. Sekedar pengetahuan di balik layar atau untuk kamu yang ingin mengimplementasikannya sendiri.

## 1. Mention target
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

## 2. Pengirim mencari endpoint webmention
Dari sisi penerima (yang ingin dimention), ia harus memberi tahu di mana 'endpoint' jika seseorang ingin mengirim webmention.

Dari sisi pengirim, harus membuka URL (fetch) target dan mencari HTTP link header dengan nilai `rel=webmention`. Jika halaman target adalah HTML maka yang dicari adalah tag `<link>` atau `<a>`.

Contoh url target yang akan difetch.  
Target, harus menyediakan hal ini.
```
GET /tulisan HTTP/1.1
Host: hilman.space
HTTP/1.1 200 OK
Link: <http://hilman.space/webmention-endpoint>; rel="webmention"

<html>
<head>
...
<link href="http://hilman.space/webmention-endpoint" rel="webmention" />
...
</head>
<body>
....
<a href="http://hilman.space/webmention-endpoint" rel="webmention">webmention</a>
...
</body>
</html>
```

Ada layanan yang membuat hal ini otomatis. Namun tentunya, developer bisa membuatnya sendiri. Silahkan menggunakan bahasa apapun yang kamu nyaman. Ini contoh menggunakan curl. 
```
curl -si https://CHANGE_WITH_URL_TARGET | grep rel=\"webmention\"
```
Kamu bisa mencoba perintah tersebut untuk target URL nya, jika target memiliki informasi `webmention`, kamu akan melihatnya, jika tidak, maka tidak ada yang dikembalikan.

Tugas kamu adalah mengambil URL dari hasil fetch tersebut dan mengirim webmentionnya ke sana.

## 3. Mengirim data webmention
Setelah mendapatkan URLnya, tugas kita sekarang adalah mengirim datanya, dengan
```
curl -i -d "source=$your_url&target=$target_url" $targets_webmention_endpoint
```
Ini adalah cara pengirim memberitahu penerima.

Bisa juga dengan mengirim form HTML dengan detail berikut
```
metode POST, mengirim x-www-form-urlencoded 
dengan parameter:
- source
- target
```

## 3.1 Update Mention
Untuk update data, pengirim harus mengirim ulang data yang ingin diubah dengan cara yang sama seperti sebelumnya.


## 3.2 Menghapus Mention
Jika URL sumbernya terhapus, maka pengirim harus mengembalikan HTTP 410 Gone. Bisa juga ditambahkan dengan menghapus property post atau kontennya menjadi kosong atau memberi nilai "DELETED" (terhapus). Jangan lupa pengirim, harus mengirim ulang webmentionnya beserta keterangan ini.

Hal ini memungkinkan penerima yang mungkin sebelumnya memakai keterangan tersebut di kolom komentar, mengubah status komentar tersebut.