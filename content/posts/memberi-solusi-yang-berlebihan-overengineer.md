+++
date = 2021-10-12T23:04:25Z
description = "Over-engineer adalah istilah ketika kita menyelesaikan suatu masalah namun dengan solusi yang berlebihan. Yuk kita bahas seputar apa itu overengineering di sini"
featured_image = "/uploads/screen-shot-2021-10-13-at-10-59-01-am.png"
slug = "overengineer"
tags = ["catatan"]
title = "Memberi solusi yang berlebihan (overengineer)"

+++
Kamu sedang ingin keluar rumah, tapi di luar hujan. Bagaimana ya biar tidak basah kuyup? Saya ada ide! bagunlah kanopi.. sampai tujuan kamu. Masalahnya selesai, kamu tidak basah lagi. Tapi.. apakah bikin kanopi adalah solusi yang tepat untuk menghindari hujan?

Yang kita lakukan di atas adalah over-engineering suatu masalah. Overengineer bisa kita artikan "Menggunakan solusi berlebihan dari yang dibutuhkan". Berlebihan di sini bisa banyak: bisa lebih mahal atau lebih kompleks.

## Contoh over-engineer pada dev

Sebagai seorang developer ada banyak kasus kita berlebihan menggunakan sesuatu. Contoh:

* Saat ingin toggle sebuah modal (open/close) kita langsung menggunakan aplikasi state management.
* Butuh membuat 1 halaman website sederhana, kita langsung mencari framework javascript.
* Saat butuh sebuah data, kita memilih menyiapkan abstraksi, API, authentikasi dan lainnya.

Tentu setiap kasus di atas akan sangat bergantung dengan konteksnya masing-masing.

## Penyebab over-engineering

Hal ini bisa dikarenakan oleh pengetahuan yang terbatas saat itu. Ada istilah "kalau orang sudah belajar memalu, semuanya terlihat seperti paku". Kita berusaha mengimplementasikan ilmu yang kita punya tanpa tahu konteks sebenarnya.

**Tidak mengetahui konteks**

Masing-masing alat (tool/library/framework) punya tujuan kenapa ia dibuat. Tidak ada satu tool untuk mengatasi semua masalah.

Untuk mengatasinya, tentu perlu mempelajari tool atau ilmu yang kita punya sekarang. Apa sih konteks ia digunakan, kapan sebenarnya solusi ini menjadi tepat.

**Tidak mencari alternatif**

Yang kedua, kita perlu mencari alternatif. Ada banyak hal yang kita tidak tahu. Karena itu perlu melihat pilihan-pilihan lain. Mungkin ada solusi yang lebih tepat.

Kita perlu terbuka dengan alat atau ide yang tidak familiar sebelumnya. Bisa jadi ini bisa jauh membuat pekerjaan kita jadi lebih mudah.

**Berlebihan memikirkan masa depan**

Kita senang membuat sebuah abstraksi, karena takut program ini akan diimplementasikan di banyak hal, lebih baik kita abstraksikan sekarang agar nanti menjadi lebih fleksibel.

Argumen ini tentu valid. Kita tidak boleh melupakan rencana dari aplikasi ini, bukan hanya saat ini saja. Kita harus tahu, apa yang akan ditambahkan nanti, dalam jangka waktu berapa lama, dan informasi lainnya. Karena itu kita perlu mempelajari kebutuhan dari aplikasi ini sedetail mungkin dari berbagai orang yang terlibat dengan proyek ini seperti klien atau bos kita.

## Toleransi over-engineer

Bagaimana dengan jaman sekarang? ketika banyak bahasa program baru, framework bahkan aplikasi yang memudahkan pekerjaan kita. Bisa jadi framework tersebut tergolong 'berat' atau aplikasinya 'mahal'. Apakah menggunakan solusi tersebut tergolong over-engineer?

**Trade-off**

Mungkin sebagai seorang developer kita bisa membuat suatu aplikasi lebih cepat dengan mempelajari bahasa low-level. Dengan ini kita membuat aplikasinya lebih hemat resources, performanya lebih baik dan gratis (karena kita buat sendiri!).

Pertanyaannya: apakah kamu rela menghabiskan banyak waktu untuk itu? mempelajari, implementasi dan proses debugnya butuh waktu yang lama.

Saat solusi yang ada sudah cukup memuaskan. Maka tidak perlu berlebihan mengejar lebih cepat 0.0005 detik tersebut, jika memang tidak dibutuhkan.

Justru 'over-engineer' adalah ketika kita menggunakan resource kita sendiri (pikiran dan waktu) untuk menyelesaikan masalahnya.

Kita harus memikirkan "tradeoff"(apa yang ditukar) dan melihat mana yang lebih menguntungkan, meskipun ada sedikit yang dikorbankan.

Contoh di atas: kita memikirkan tradeoff antara belajar bahasa low-level jaman dulu untuk membuat aplikasi lebih cepat 1/2 detik.

Apakah 1/2 detik ini benar-benar diperlukan di aplikasi kamu? jika tidak, maka tidak perlu melakukan hal tersebut.

**Terbatasnya waktu dan kondisi**

Bisa juga penyebab over-engineer karena kita tidak punya waktu untuk mencari alternatif lain. Akhirnya kita hanya membuat berdasarkan pengetahuan yang ada. Mungkin di kasus ini bisa 'dimaafkan'.

## Overengineer pada fitur

Overengineer bukan hanya pada solusi, tapi juga pada fiturnya. Bisa jadi implementasi teknologinya sederhana, namun fitur yang kita hadirkan justru membuat sesuatu lebih kompleks dari yang dibutuhkan. Kita juga perlu berhati-hati, jangan sampai implementasi solusinya yang berlebihan.

## Kesimpulan

Kita perlu melihat over-engineer dari perspektif seorang developer dengan berbagai konteksnya: berapa lama waktu yang disediakan, berapa budget yang tersedia dan konteks lainnya. Setelah itu kita bisa memikirkan apakah ada cara yang lebih mudah untuk "membuat aplikasi" ini tanpa melupakan proses pengembangan ke depannya.