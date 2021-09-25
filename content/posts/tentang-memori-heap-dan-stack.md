+++
date = 2021-09-24T16:00:00Z
description = "Berkenalan apa itu memori heap dan memori stack. Apa perbedaannya dan kapan menggunakan salah satunya."
featured_image = ""
slug = "heap-dan-stack"
tags = ["catatan"]
title = "Tentang memori Heap dan Stack"

+++
Saat sedang belajar bahasa program Rust, saya bertemu dengan materi Ownership. Materi ini membahas fitur Rust seputar alokasi memori. Karena tidak mau terima begitu saja, saya mundur sedikit _masalah apa sih yang ownership selesaikan?_.. ternyata seputar memori heap dan stack.

**Tidak tahu apa itu memori heap dan stack?**  
saya juga!

Dapatlah bahan belajar baru yang akan saya tuangkan di sini. Tulisan tentang memori heap dan stack

## Kenapa saya tidak pernah mendengranya?

"Tidak pernah mendengar" mungkin sedikit berlebihan, lebih tepatnya jarang. Alasannya karena selama ini urusan memori saat menjalankan suatu program hanya ada saat  berkutat dengan "low level language".

Semua ada untung-ruginya. Saat ingin menggunakan bahasa program yang terkenal dengan kecepatan layaknya "Rust" pasti ada hal seperti ini yang tidak kita temui sebelumnya. Karena itulah perlu sedikit memahami konsep ini, agar tidak asal memakai bahasanya nanti.

## Apa sih heap dan stack

Ini adalah cara bahasa program menyimpan suatu data di memory. Bukan database, tapi data-data dari program yang kita tulis itu sendiri.

Cara penyimpannya di memori ada dua jenis: Stack dan Heap

Kalau digambarkan kira-kira seperti ini:
{{< rawhtml >}}
<div>
<img src="https://i.ibb.co/w64Q6pP/heao.png" alt="gambar heap" width="200" height="200">
<img src="https://i.ibb.co/9cLjzGg/stack.png" alt="gambar stack" width="200" height="200">
</div>
{{< /rawhtml >}}

## Apa itu Stack

Stack menyimpan data berdasarkan urutan masuknya. Bayangkan piring yang ditumpuk. Pasti cara menumpuknya harus ke atas (bukan menyelipkan ke bawah).

Cara mengambilnya sebaliknya, kita kenal dengan LIFO (last in first out) alias yang terakhir masuk, akan pertama keluar. Ingat tumpukan piring, cara ambilnya harus dari atas.

{{< rawhtml >}}
<div>
<img src="https://i.ibb.co/9cLjzGg/stack.png" alt="gambar stack" width="200" height="200">
</div>
{{< /rawhtml >}}

**Ciri-ciri stack:**

* Data yang disimpan ukurannya sudah ketahuan
* Ukuran data tidak boleh berubah
* Biasanya berjalan otomatis
* Menyimpan dan mengambil data lebih cepat (karena sudah jelas prosedurnya ditumpuk seperti piring)

## Apa itu Heap

Sementara heap, bayangkan kamu masuk ke restoran. Pelayannya akan bertanya "berapa orang Pa?". Tempat duduk kamu akan disesuaikan dengan jumlah kursi dan orangnya.

Menyimpan data di heap sering diikat dengan kata 'allocating'. Karena kita harus secara khusus mencarikan tempat untuk data tersebut. Setiap meja di restoran ada nomor atau kodenya. Nomor ini kita sebut sebagai address/pointer yang mewakili meja tersebut.

{{< rawhtml >}}
<div>
<img src="https://i.ibb.co/w64Q6pP/heao.png" alt="gambar heap" width="200" height="200">
</div>
{{< /rawhtml >}}

**Ciri-ciri Heap:**

* Data bisa tidak diketahui ukurannya
* Ukuran data bisa berubah
* Biasanya perlu dikerjakan sendiri oleh programmernya
* Menyimpan dan mengambil data butuh kerja extra (karena butuh tempat khusus, tidak ada urutan)

## Kapan menggunakan Heap, kapan Stack

Kasarnya sih.. kamu pakai stack saat sudah tahu berapa banyak data yang dibutuhkan sebelum compile berjalan dan ukurannya tidak terlalu besar. Heap sebaliknya.

## Contoh kongkrit heap dan stack?

Contohnya kamu mau menyimpan angka

    let x = 10;

Karena nilainya sudah diketahui dan relatif kecil, ini disimpan di stack.

Sementara, saat kamu misalnya ingin menerima sesuatu dari input user

    let input = InputFromUser()

Nilainya cenderung tidak diketahui, kita menyimpannya di heap.