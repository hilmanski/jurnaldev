---
title: "Kalkulator Modal Jualan Makanan"
date: 2021-09-24T13:17:25+08:00
description: "Bagaimana cara menghitung harga jualan makanan berdasarkan modal. Coba Kalkulator bahan makanan ini"
tags: ["random"] 
featured_image: https://i.ibb.co/4gCGbFp/Screen-Shot-2021-09-24-at-2-34-31-PM.png
---

Jika bingung, baca cara menggunakannya di bawah kalkulator.

## Kalkulator
{{< rawhtml >}}
<section id="calculator">
<div class='is-center'>
	<h3> 📲 Kalkulator, Mari kita coba! </h3>
</div>

<div id="forms">
	<div class="form_row">
		<label>Bahan: </label><br>
		<input class='input_name' type="text" placeholder="Nama bahan"/>
		<input class='input_price' type="number" placeholder="Harga bahan"/>
		<input class='input_qt_total' type="number" placeholder="Total bahan"/>
		<input class='input_qt_usage' type="number" placeholder="Yang digunakan"/>
	</div>
</div>

<hr>
<button id="addform_btn" onclick="addForm()">+ Bahan baru</button>	
<div class="clearfix">
	<button id="total_btn" onclick="countCapital()">Hitung Modal</button>	
</div>

<div id="result"></div>

</section>


<script>
	function addForm() {
		const clone = document.getElementsByClassName('form_row')[0].cloneNode(true)
		document.getElementById('forms').appendChild(clone)
	}

	function countCapital() {
		const rows = document.getElementsByClassName('form_row')
		let costPerUnit = []
		let textExplanation = '<p>Rincian: </p>'
		for (var i=0; i<rows.length; i++) {
			let name = rows[i].querySelector('.input_name').value
			let price = rows[i].querySelector('.input_price').value
			let qt_total = rows[i].querySelector('.input_qt_total').value
			let qt_usage = rows[i].querySelector('.input_qt_usage').value

			let cost_unit = (qt_usage / qt_total) * price
			costPerUnit.push( cost_unit )
			textExplanation += `<li>${name} -> harga bahan yang dipakai = ${cost_unit.toFixed(2)}</li>`
		}

		const sum = costPerUnit.reduce((a, b) => a + b, 0)
		
		let summaryText = `<p><b>Modal makanan per porsi = ${formatPrice(sum)}</b></p>` + textExplanation
		document.getElementById('result').insertAdjacentHTML('beforeend', summaryText)
	}

	function formatPrice(num) {
		let formatNum = new Intl.NumberFormat('id-ID').format(num.toFixed(2))
		return 'Rp.'+formatNum
	}
</script>

<style>
input {
	padding: 5px 2px;
}
#calculator {
	margin: 40px 0;
	background: #eee;
	padding: 20px;
	border: 2px solid #2755EE;
}
.form_row {
	margin-bottom: 10px;
}
button{
	border: none;
	border-radius: 5px;
}
#addform_btn{
	float: right;
	background: #537DEE;
	color:  white;
	padding: 5px;
}
#total_btn{
	margin-top: 20px;
	width: 100%;
	padding: 10px;
	margin-bottom: 20px;
	background: #2755EE;
	color:  white;
}
.clearfix::after {
  content: "";
  clear: both;
  display: table;
}
</style>
{{< /rawhtml >}}

Kalkulator menghitung harga jual minimal makanan berdasarkan modal bahan.  

## Cara Menggunakan
**Contoh kasus**  
Kamu mau masak "kue XYZ".  
Kue XYZ butuh 2 telur dan 200gr tepung.    

**Bahan yan harus dibeli:**  
Telur 1 rak = 30 butir = Rp.40.0000  
Tepung 1 kg = 1000 gr = Rp.20.0000  
 
**Maka, masukkan di kalkukator:**  
```
Nama   | Harga | Total  | Yang digunakan
-----------------------------------------
Telur  | 40000 | 30     |  2  
Tepung | 20000 | 1000   |  200  

*harga tidak perlu pakai Rp, koma atau titik
*satuan takaran tidak perlu ditulis
```

## Disclaimer
Ini adalah bahan yang bisa dihitung saja.  
Hitung modal tentu bukan hanya bahannya saja.
Ada biaya lain, seperti:
- Tenaga kerja
- Modal alat
- Biaya operasional (listrik, gas, etc.. )  

**Terima Kasih!**  
Bagikan link kalkulator ini  
ke keluarga atau teman kamu yang membutuhkan :)
