---
title     : Inkscape - Fitur Teks
date      : 2016/11/01 09:17:35
tags      : [inkscape, alumni]
category  : [desain]
keywords  : [text feature]

toc       : "toc/2015-inkscape-alumni"
---

<a name="prakata"></a>

## Prakata

Inkscape memiliki banyak fitur.
Fitur teks ini sangat sederhana.
Yang dibutuhkan hanyalah penyesuaian karakter di teks,
apakah itu `spacing`, atau `kerning` atau rotasi.
Tidak dibutuhkan keahlian khusus, namun harus dilakukan secara manual.
Batasnya adalah imajinasi pembaca.
Tujuan penulis adalah memberikan template gratisan di sini,
dan bukanlah bahan ajar yang lengkap.
Untuk rincian lebih lanjut, pembaca dapat membaca ini terlebih dahulu.

* <https://design.tutsplus.com/tutorials/kerning-spacing-and-other-text-tricks-in-inkscape--cms-20576>

Pembaca dapat memilih untuk mengabaikan keseluruhan tutorial tak berguna ini,
dan langsung saja mengunduh sumber image dalam bentuk SVG.
Penulis tidak berkeberatan

* [akutidaktahu/.../dukungan-pribadi-01.svg.zip][dotfiles-sample-3]

### Daftar Isi

* [Prakata](#prakata): Daftar Isi

* [Teks: Shift dan Rotation](#teks)
* 1: [Contoh 1: UU Kemaritiman?](#contoh-satu)
* 2: [Contoh 2: Penegakan Hukum](#contoh-dua)
* 3: [Contoh 3: Lebih lanjut dari Contoh 2](#contoh-tiga)

* [Penutup](#penutup)

### Bahasa Inggris

Artikel ini juga disajikan di blog penulis yang lain,
dalam bahasa Inggris:

* [Inkscape: Text Feature][english-version]

-- -- --

<a name="teks"></a>

## Teks: Shift dan Rotation

Suatu contoh sederhana.

### Langkah Pertama

* Buatlah berkas inkscape baru, dengan lebar 200px, dan tinng 200px.

* Buat kotak, tanpa latar belakang memenuhi semua area halaman,
  kita membutuhkan ini untuk meratakan `align` pada teks.

* Buat teks `abc` di dalam area kota di atas, dengan ukuran fonta sekitar 80px.

* Ratakan `align` teks tersebut,
  di tengah secara vertikal maupun horisontal,
  menggunakan kotak sebelumhya sebagai panduan.

![Rotation Step One][image-text-1]

Kil ganda teks `abc` di atas, maka akan tampak toolbar.

![Rotation Toolbar One][image-toolbar-1]

### Tahap Kedua

Klik ganda text `abc`.
Dan soroti `highlight` karakter `b`.
Lalu ubah teks dengan emnggunakan toolbar.

* Vertical shift: 3px

* Character Rotation: 5 degrees

![Rotation Toolbar Two][image-toolbar-2]

Hasilnya akan berubah seketika.

![Rotation Step Two][image-text-2]

### Tahap Ketiga

Klik ganda text `abc`.
Dan soroti `highlight` karakter `c`.
Lalu ubah teks dengan emnggunakan toolbar.

* Vertical shift: 6px

* Character Rotation: 10 degrees

![Rotation Toolbar Three][image-toolbar-3]

Pembaca dapat melihat hasil akhirnya.

![Rotation Step Three][image-text-3]

Simpan berkas, bilamana perlu.
Atau silahkan unduh SVG di bawah:

### Berkas Sumber SVG

* [akutidaktahu.netlify.app/.../text-feature.svg][dotfiles-sample-0]

-- -- --

<a name="contoh-satu"></a>

## Contoh 1: UU Kemaritiman?

Ini berkas lawas dari e-Flyer yang benar saya sebarkan di tahun 2014.
Terlalu sederhana untuk di dikoumentasikan.

![UU Kemaritiman ?][image-sample-1]

### DeviantArt

* [nurwijayadi.deviantart.com/art/...][deviant-sample-1]

-- -- --

<a name="contoh-dua"></a>

## Contoh 2: Penegakan Hukum

Kalau yang ini cenderung ke konsep,
dan secara praktis sebetulnya kurang berguna.
Maksud penulis adalah, ini hanya contoh,
dari sini pembaca dapat mengubah teks, warna,
dan tentunya keseluruhan pesan.
Yang perlu diingat dalah penyesuaian antara teks dengan ukuran berkas.
Pembaca perlu mempertimbangkan jumlah karakter.
Salah satu trik yang dapat dipakai adalah mengubah ukuran font.
Sesederhana itu.

![Penegakan Hukum][image-sample-2]

### Properti Berkas

**Ukuran**: lebar 500px, tinggi 600px

### Tata Huruf

Semua menggunakan font yang bebas diunduh.

* Capture It <http://www.dafont.com/capture-it.font: Text Shape>

* Sablon Up <http://www.dafont.com/sablon-up.font>

* Oswald <https://fonts.google.com/specimen/Oswald>

### Efek Filter

* Drop Down Shadow: Color: black (#000000), Opacity: 0.5, Blur: 10px, Offset-X: 20, Offset-Y: 20

### Warna

Awalnya penulis memakai palet dari `google material design`.
Namun kemudian penulis berniat memakai warna `maroon` saja,
dengan mengubah bagian warna merah dari RGB, menjadi setngah dari nilai awalnya.

Ada juga gradien radial kelabu, dari tengah (#ffffffff),
ke luar (#c8c8c8ff). Ini tampak lebih bagus dari sekedar putih saja.

### DeviantArt

* [nurwijayadi.deviantart.com/art/...][deviant-sample-2]

-- -- --

<a name="contoh-tiga"></a>

## Contoh 3: Lebih lanjut dari Contoh 2

Seperti telah dijanjikan, pemirsa di sini tidak akan pergi sia-sia,
tanpa SVG template yang dapat diunduh.
Mari kita berjalan lebihjauh, dan menambahkan identitas.
Supaya pembaca dapat menggunakan template ini,
untuk kegiatan kampus sendiri,
atau sebagai kartu identitas dalam suatu eksibisi,
atau apapun itu, terserah kalian.

Mari, tempatkan tiap-tiap bagian di dalamlapisan `layer` masing-masing,
supaya pengguna dapat mengubah dengan mudah baik warna maupun pola di dalamnya.
Penulis juga menaruh teks `watermark`,
sebagai ID dari berkas supaya kelihatan profesional.
Pengguna dapat memadamkan lapisan `layer` ini di kemudian hari.
Yaitu saat pengguna dan tim di organisas,
sudah cukup yakin untuk menyetujui rancangan desain ini.

![Penegakan Hukum][image-sample-3]

### Rancangan

Berkas inkscape ini mewarisi semua properti dari contoh sebelunya.

### Efek Filter

Penulis menginginkan teks identitas supaya kecil.
Ditaruh di bawah teks utama.
`blur` maupun angak `offset`, harus lebihkecil dari teks utama.

* Drop Down Shadow: Color: black (#000000), Opacity: 0.5, Blur: 3px, Offs.et-X: 5, Offset-Y: 5

### DeviantArt

* [nurwijayadi.deviantart.com/art/...][deviant-sample-3]

### Berkas Sumber SVG

Bilamana pembaca meng-klik gambar SVG ini dibrowser,
dan kemudian fonta-nya terlihat aneh,
maka pembaca harus mengunduh fonta yang tepat, dan menempatkannya di dalam sistem.

* [akutidaktahu.netlify.app/.../dukungan-pribadi-01.svg.gz][dotfiles-sample-3]

Supaya aman, penulis kompres saja berkas tersebut.

-- -- --

<a name="penutup"></a>

## Penutup

Begitu saja ya bang.
Saya juga tidak paham nih.

[//]: <> ( -- -- -- links below -- -- -- )

[english-version]:  https://epsi-rns.gitlab.io/design/2016/11/01/inkscape-text-feature/

[image-text-1]:     /posts/desain/2016/11-teks/text-feature-1.png
[image-text-2]:     /posts/desain/2016/11-teks/text-feature-2.png
[image-text-3]:     /posts/desain/2016/11-teks/text-feature-3.png

[image-toolbar-1]:  /posts/desain/2016/11-teks/text-feature-toolbar-1.png
[image-toolbar-2]:  /posts/desain/2016/11-teks/text-feature-toolbar-2.png
[image-toolbar-3]:  /posts/desain/2016/11-teks/text-feature-toolbar-3.png

[image-sample-1]:   /posts/desain/2016/11-teks/uu-kemaritiman.png
[image-sample-2]:   /posts/desain/2016/11-teks/penegakan-hukum-01.png
[image-sample-2b]:  /posts/desain/2016/11-teks/penegakan-hukum-02.png
[image-sample-3]:   /posts/desain/2016/11-teks/dukungan-pribadi-01.png

[dotfiles-sample-0]: /posts/desain/2016/11-teks/text-feature.svg
[dotfiles-sample-2]: /posts/desain/2016/11-teks/penegakan-hukum.svg
[dotfiles-sample-3]: /posts/desain/2016/11-teks/dukungan-pribadi-01.svg.zip

[deviant-sample-1]: http://nurwijayadi.deviantart.com/art/Undang-Undang-Kemaritiman-645790906
[deviant-sample-2]: http://nurwijayadi.deviantart.com/art/Penegakan-Hukum-645722442
[deviant-sample-3]: http://nurwijayadi.deviantart.com/art/Dukungan-Pribadi-645721708
