---
title     : Spreadsheet - Formula Tarif Progresif
date      : 2019/09/10 09:17:35
tags      : [spreadsheet, infografis]
category  : [pajak]
opengraphimage: /posts/2019/09/formula-progressive.png
---

Menurunkan rumus matematika,
untuk mendapatkan formula yang sederhana,
yaitu untuk menghitung tarif progresif,
yang ada di pasal 17.
<!-- more -->

### Latar Belakang 

Pertama kali saya menghitung pajak pribadi sangatlah mudah,
karena di bawah PTKP. Berikutnya tetap mudah karena hanya dipotong 5%.
Sesuai aturan pajak progresif sebagai berikut:

```
   0 sd 50  juta:  5%
> 50 sd 250 juta: 15%
>250 sd 500 juta: 25%
selanjutnya     : 30%
```

Tiba saatnya bekerja bersama rekan,
saya menghitung PPH 21 dengan tarif pasal 17 yaitu 15%,
karena akibat bonus project dalam bulan tersebut,
penghasilan kena pajak yang disetahunkan,
ternyata sudah lebih dari dua ratus lima puluh juta rupiah.
Tiba saatnya saya mencari formula yang tepat,
untuk pekerjaan mencari tarif progresif ini,
yang terdiri dari beberapa tingkat,
yaitu 5%, 15%, 25% dan 30%.

#### Permasalahan

Bagaimana cara menghitung dengan cepat di lembar kerja spreadsheet?

Tentu saja perhitungan dapat dibuat dengan tabel,
yang cocok untuk menghitung satu sampai tiga rekan kerja,
namun ini menjadi tidak efisien, 
dalam pekerjaan sehari-hari bilamana karyawan sudah banyak.

Menghitung cepat dapat dilakukan bilamana perhitungan cukup dilakukan,
dengan hanya formula pendek.

#### Referensi

Sebetulnya saya pemakai LibreOffice Calc.,
namun referensi terbaik yang saya dapatkan adalah dari situs ini:

* [Rumus Excel PPh 21](https://excelku.com/2015/03/15/rumus-excel-pph-21/)

#### Artikel Terkait

Saya juga membikin artikel berbahasa inggris di blog saya yang lain,
yaitu mengenai perhitungan tarif progresif,
dengan menggunakan Haskell (pure functional programming).

* [Haskell - Tax Tariff](https://epsi-rns.gitlab.io/code/2019/09/01/progressive-tax-tariff-01/)

-- -- --

### Rumus Pendek

Jawaban singkatnya adalah

{% codeblock lang:haskell %}
=max( ({5;15;25;30}%*$PPh) - {0;5;30;55}*10^6 )
{% endcodeblock %}

Sebagai perbandingan ada juga cara lain,
yang lebih panjang.

{% codeblock lang:haskell %}
=ifs($PPh<=(50*10^6),  $PPh*5%,
     $PPh<=(250*10^6), $PPh*15%-5*10^6,
     $PPh<=(500*10^6), $PPh*25%-30*10^6,
     1,                $PPh*30%-55*10^6
    )
{% endcodeblock %}

Fungsi IFS ini ada LO Calc atau MS Excel 2019.

#### Infografis

Secara ringkas,
maka rangkuman dalam gambar infografis
dari formula tarif progresif pasal 17
adalah sebagai berikut:

![Infografis: Formula Tarif Progresif Pasal 17][tarif-progresif-infografis]

#### Source Gambar

Barangkali perlu, maka source infografis ada di sini:

* [Source SVG: Formula Tarif Progresif Pasal 17][tarif-progresif-source-svg]

#### Contoh Perhitungan

{% codeblock lang:haskell %}
PKP = 200 juta

PPh = 15% * 200 juta - 5 juta
    = 30 juta - 5 juta
    = 25 juta
{% endcodeblock %}

T2 Langsung saja dikurangi 5 juta, langsung ditemukan jawabnya.

Mudah bukan!

#### Spreadsheet

Libreoffice Calc.

* [Libreoffice Calc: Formula Tarif Progresif][tarif-progresif-libreoffice]

Microsoft Excel.

* [Microsoft Excel: Formula Tarif Progresif][tarif-progresif-ms-office]

-- -- --

### Perbandingan dengan Metode lain

Beberapa cara yang saya coba membutuhkan beberapa baris,
di lembar kerja spreadsheet,
yang beberapa diantaranya saya ambil dari referensi ini:

* [Rumus Excel PPh 21](https://excelku.com/2015/03/15/rumus-excel-pph-21/)

Semua di bawah ini menggunakan fungsi `sum` atau `sumif`,
sehingga tidak dapat dijadikan satu baris fungsi pendek yang sederhana.

#### 01: Mencari Range

![Tarif Progresif: Table][tarif-01-table]

#### 02: Sum antara Max dan Min

![Tarif Progresif: Sum antara Min and Max][tarif-02-between]

#### 03: Sumif dan Min

![Tarif Progresif: Sumif dan Min][tarif-03-sumif]

#### 04: Sumif dan If

![Tarif Progresif: Sumif dan If][tarif-04-sumif]

#### 05: Match dan Index

![Tarif Progresif: Match dan Index][tarif-05-match]

#### 06: Sum Min

Conditional Range

![Tarif Progresif: Sum Min][tarif-06-sum-min]

#### 07: Sum Min Max

Conditional Range

![Tarif Progresif: Sum Min Max][tarif-07-min-max]

#### 08: Sum Min

Dengan Pengurang

![Tarif Progresif: Sum Min][tarif-08-sum-min]

#### 09: Sum Max

Dengan Pengurang

![Tarif Progresif: Sum Max][tarif-09-sum-max]

-- -- --

### Kendala Menemukan Rumus dalam Satu Baris

> Cara berfikir procedural dan functional memang berbeda.

Untuk mendapatkan rumus pendek dalam satu baris,
maka perlu memakai array dengan melakukan `sumproduct`.
Yang menjadi kendala dalam penggunaan `sumproduct` ini adalah,
array tidak dapat berada dalam fungsi `max`, `min` ataupun `if`.

Penggunaan array di dalam conditional `max` dapat dilakukan,
bilamana array di dalamnya tidak berada dalam fungsi lain.

-- -- --

### Kesimpulan

Nah sekarang, kalau aturan pasal 17 ini diubah,
yaitu dengan naskah RUU yang baru,
maka teman2 dapat membikin rumus sendiri khan ?

[//]: <> ( -- -- -- links below -- -- -- )

[tarif-progresif-infografis]:   /posts/pajak/2019/09/formula-progressive.png
[tarif-progresif-source-svg]:   /posts/pajak/2019/09/formula-progressive.svg
[tarif-progresif-libreoffice]:  /posts/pajak/2019/09/hitung-tarif-progresif.ods
[tarif-progresif-ms-office]:    /posts/pajak/2019/09/hitung-tarif-progresif.xls

[tarif-01-table]:   /posts/pajak/2019/09/01-table.png
[tarif-02-between]: /posts/pajak/2019/09/02-between.png
[tarif-03-sumif]:   /posts/pajak/2019/09/03-sumif-min.png
[tarif-04-sumif]:   /posts/pajak/2019/09/04-sumif-if.png
[tarif-05-match]:   /posts/pajak/2019/09/05-match-index.png
[tarif-06-sum-min]: /posts/pajak/2019/09/06-sum-min.png
[tarif-07-min-max]: /posts/pajak/2019/09/07-sum-min-max.png
[tarif-08-sum-min]: /posts/pajak/2019/09/08-sum-min.png
[tarif-09-sum-max]: /posts/pajak/2019/09/09-sum-max.png
