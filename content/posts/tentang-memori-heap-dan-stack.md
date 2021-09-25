+++
date = 2021-09-24T16:00:00Z
description = "Berkenalan apa itu memori heap dan memori stack. Apa perbedaannya dan kapan menggunakan salah satunya."
draft = true
featured_image = ""
slug = "heap-dan-stack"
tags = []
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

![](https://i.ibb.co/w64Q6pP/heao.png)

![](https://i.ibb.co/9cLjzGg/stack.png)