---
title     : Inkscape - Gambar Latar Isometrik Datar
date      : 2016/10/03 09:17:35
tags      : [inkscape]
category  : [desain]
keywords  : [material design, wallpaper, flat design]

toc       : "toc/2015-keseharian"
---

### Prakata

Apa!! Proyeksi isometri 3D di bidang datar 2D?
Oh, sebetulnya ini sama sekali bukan proyeksi 3D.
Hanya kebetulan penulis memakai perspektifnya,
untuk membuat jaring `grid` yang sesuai.
Supaya hasilnya tampak anggun.

Tanpa proyeksi isometri,
yang dibutuhkan hayalah memutar `rotasi`, bentuk `shape` dan teks.
Namun dengan isometri, kita perlu mencondongkan `skew` terlebih dahulu,
sebelum memutar objek.
Keuntungan dari tampilan condong ini adalah,
lebih memiliki tampilan yang realistis,
sebagaimana terlihat di tampilan berikut:

![Pratili Gambar Latar][image-preview]

#### Bahasa Inggris

Artikel ini juga disajikan di blog penulis yang lain,
dalam bahasa Inggris:

* [Inkscape: Flat Wallpaper with Isometric Looks][english-version]

-- -- --

### Template

Awali dengan membuat berkas baru, untuk gambar latar `wallpaper` ini.

#### Halaman

Ubah properti berkas supaya sesuai dengan ukuran layar yang extra lebar.

* Satuan Baku: px

* Lebar: 1920 px

* Tinggi: 1080 px

![Properti Berkas: Halaman][image-dialog-page]

#### Kisi Grid

Buka properti berkas, can bikinlah `Axonometric Grid` yang baru.

* Satuan kisi `grid`: px

* Jarak `spacing` Y: 32

* Sudut `angle` X: 30

* Sudut `angle` Z: 30

* Kisi utama `major grid`: 4

Periksalah pilihan menu (<kbd>View - Page Grid</kbd>)
untuk menampilkan kisi `grid` di halaman pembaca.
Perhatikan bahwa jarak `spacing` dan kisi utama `major grid`,
bersifat luwes dan dapat diubah kapan saja.
Aturanya adalah, pilih yang cocok untuk karya yang sedang dikerjakan.
Sebagai tambahan, sobat pembaca dapat mengubah berkas `XML`,
dan kemudian menamai kisi `grid` dengan nama tertentu,
misalnya `Isonometric`.

![Properti Berkas: Kisi Grids][image-dialog-grids]

#### Palette

Persiapkan palet warna.
Di sini kita akan menggunakan `Google Material Pallete`.

![Pallete: Google Material][image-pallete]

#### Patokan Snaps

Persiapkan patokan `snaps`, dengan meng-klik `icon` terkait.

* Snap Bounding Boxes.

* Snap Nodes, Path and handles.

#### Lapisan Layer

Bikinlah tiga lapisan `layer` baru.

* Crop

* Wallpaper

* Background

![Dock: Lapisan Layers][image-dock-layers]

#### Lapisan Layer: Latar Background

Pilihlah latar background sebagai ruang kerja saat ini.
Perbesar `zoom` tampilan atau klik (<kbd>5</kbd>),
dan perbesar `zoom` beberapa kali seperlunya.
Kita akan membikin latar background dengan bentuk isometrik,
menggunakan`Freehand Lines` (<kbd>F6</kbd>).

Tarik gambar `path` dengan menekan  (<kbd>F6</kbd>),
lalu atur patok `snap` ke `Handle to Grid Intersection`.
tepat di kisi utama `major grid` yang pertama,
kira-kira di bagian kiri-bawah dari halaman.
Gagasannya adalah, latar belakang `background`,
harus menutupi semua bidang halaman.

![Tuas Patok: Snap Handle][image-snap-handle]

Klik dari simpul `node` ke simpul `node` yang lain,
sampai sobat pembaca berhasil mendapatkan bentuk berlian.
Sekarang sobat pembaca memiliki pola ubin,
sebanyak kira-kira 18 kotak x 19 kotak.
Tuang dengan warna apapun yang dikehendaki,

Kunci lapisan `layer`, setelah selesai.

#### Lapisan Layer: Crop

Gunakan lapisan `layer` bernama `crop` sebagai ruang kerja saat ini.
Sembari bekerja, kita butuh untuk menampilkan ,
asil akhir gambar latar `wallpaper`,
tanpa pemotongan `cropping` yang sebenarnya.

Bikinlah kotak bagian dalam,
dengan ukuran dimensi yang sama dengan halaman.
Pastikan tidak ada warna pinggiran `stroke`.

* X: 0px, Y: 0px, W: 1920px, H: 1080px

![Crop: Kotak Bagian Dalam][image-box-inner]

Bikinlah kotak bagian luar,
dengan ukuran dimensi dua kali kotak bagian dalam yang tadi.
Kalau penulis, lebih suka menggandakan dengan `duplicate`,
lalu mengubah ukurannya.

* X: -960px, Y: -540px, W: 3840px, H: 2160px

Turunkan objek kotak bagian luar tadi,
menjadi di bawah kotak bagian dalam (<kbd>Page Down</kbd>).
Pilih kedua kota, dan pilih menu  (<kbd>Path - Difference</kbd>)
untuk membikin suatu kotak kopong yang bolong berlubang.

Sekarang, dengan adanya kotak kopong ini,
ubahlah `opacity` menjadi 50%.

![Crop: Kotak Bagian Luar][image-box-outer]

Dan jangan lupa untuk mengunci lapisan `layer` ini.

#### Simpan Pekerjaan

Selamat, sekarang sobat pembaca sudah punya template.
Simpanlah, `save` ke berkas baru,
misalnya dengan nama `flat-isometric-looks.svg`.

-- -- --

### Bentuk Shape Dasar

Contoh yang penulis punya ini,
terilhami dari `+ArtentDesigns` yang cemerlang.
Namun kali ini, kita akan menggunakan tampilan proyeksi isometrik.

Mari gunakan lapisan `layer` wallpaper sebagai ruang kerja saat ini.
Kita akan menggamabar balok demi balok.

#### Balok Pertama

Tarik gambar `path` dengan `Freehand Lines` dengan menekan (<kbd>F6</kbd>),
lalu bikinlah kotak isometrik dengan menggunakan patokan kisi utama `major grid snap`.
dengan kira-kira 18 kotak x 2 kotak, dari ubin utama.
Pastikan tidak ada warna pinggir `stroke`.

Tarik gambar `path` bagian dalam,
dengan kira-kira 18 kotak utama x 6 kotak tambahan.
Tanpa warna pinggir `stroke`.

Pilih keduanya, dan guguskan `group` keduanya.
Kita membutuhkan kotak bagian luar ini sebagai panduan untuk patokan `snap`.

![Balok: Pertama][image-bar-first]

#### Balok-balok Selengkapnya

Atur patok ke 'Snap Bounding Box Corner',
dan gandakan `duplicate` balok pertama untuk memenuhi,
semua bidang di latar belakang `background`.

Pilih semua dengan `select all`,
lepaskan gugus dengan `ungroup`.
Lalu hilangkan semua balokbalok yang besar.

![Balok-Balok: Selengkapnya][image-bar-all]

#### Balok Menyilang

Lakukan lagi hal yang sama,
dengan menggandakan `duplicate` maupun mencerminkan `mirror`.
Tujuannya untuk membuat balok-balok ini saling menyilang.
Penulis lebih suka melakukan dari awal.

Hilangkan balok-balok yang tidak diperlukan
Penulis lebih suka memindahkan, daripada menghilangkan,
yaitu dengan memindahkan ke kiri atau kanan,
dengan satuan pixel yang presisi,
misalnya 2000px ke kanan atau -2000px ke kiri.
Supaya dapat dikembalikan dengan mudah.
barangkali saja penulis membutuhkannya kembali di kemudian hari.

![Balok: Saling Silang][image-bar-cross]

-- -- --

### Pewarnaan

#### Latar Background

Dahulukan yang utama, gunakan putih polos, untuk latar background.

#### Balok-balok

Sisanya, penulis akan menggunakan `Google Material Color`.
Karena penulis menyukai warna lembut dari palet ini.

Balok Kiri, gunakan warna kelabu,
yang paling dalam adalah yang paling gelap.
Dan pembaca dapat menggunakan warna aksen bila menghendaki.

Balok Kiri.
1: grey 500,
2: grey 600,
3: grey 700,
4: grey 800,
5: lightblue 900,
6: grey 800,
7: grey 700,
8: grey 600,
9: grey 500,
10: grey 400.

Balok Kanan.
1: grey 900,
2: grey 700,
3: grey 900.

![Balok: Pewarnaan][image-bar-color]

#### Bayangan Shadow

Pilih semua balok, dan terapkan saringan `filter` dengan meng-klik menu.
(<kbd>Filters - Shadows and Glows - Drop Shadow</kbd>)

![Dialog: Shadow][image-dialog-shadow]

* Kabur `blur`: 10px

* Mendatar `horizontal offset`: 20px

* Tegak lurus `vertical offset`: 20px

* Jenis bayangan `shadow type`: Outer

* Warna `color`: RGBA #00000080

Ubahlah juga peletakan tumpukan objek dnegan memilih objek,
dan kemudian menekan (<kbd>Pg Up</kbd>) atau (<kbd>Pg Down</kbd>).

![Balok: Bayangan][image-bar-shadow]

-- -- --

### Teks

Ini bagian yang berat,
karena penulis tidak pandai dalam berpuisi.
Penulis harus menjenguk ke kenangan masa lalu,
untuk mencari paduan kata yang tepat.

#### Tata Huruf

Penulis menggunakan fonta `oswald`, dengan ukuran 80px, dan warna  `grey50`.
Pembaca dapat menggunakan pengauran sendiri sesuai dengan yang dikehendaki.

#### Proyeksi Isometri

Aturannya sederhana.

* Condongkan `skew`: 30 Degree, lalu putar `rotate`: 30 Degree, sesuai urutan ini. Atau

* Condongkan `skew`: -30 Degree, lalu putar `rotate`: -30 Degree, sesuai urutan ini.

![Dock: Transform][image-dock-transform]

Letakkan teks di balok menggunakan `Bounding box corner to grid intersection`.

![Teks: Patok Snap][image-text-snap]

-- -- --

### Hasil Akhir

Ekspor ke PNG, menggunakan 90dpi untuk mendapatkan lebar 1920px x tinggi 1080px.

Jangan lupa, berkas gambarnya disimpan.

#### Pratilik

![Hasil Akhir Gambar Latar][image-final]

#### Berkas Sumber SVG

Pembaca dapat meninjauulang bahan ajar ini dengan berkas sumber SVG berikut:

* [akutidaktahu.netlify.app/.../flat-isometric-looks.svg.gz][dotfiles-final]

-- -- --

### Di Luar Desain Datar

Bilamana sobat pembaca menghendaki tampilan yang lebih nyata,
dengan meninggalakan filosofi `flat designn`.
Maka sobat pembaca dapat menggunakan efek `filter`,
yang akan membuat balok tampak seperti pita.

Pembaca perlu menggandakan tiap-tiap pita,
sehingga ada pita yang di atas dan ada yang di bawah.

* Bawah: Filter - Shadows and Glows - Drop Shadow. 

* Atas: Morphology - Posterized Blur

Kita juga perlu menggelapkan warna pita.
Misalnya dengan pita yang memiliki warna `red800`,
maka warna di bawahnya harus ditingkatkan menjadi `red900`.

![Ribbon Wallpaper][image-ribbon]

#### DeviantArt

Penulis juga menaruh dua tautan, dan contohlain di `DeviantArt`.
Masing-masing dengan SVGs yang dapat di-unduh.

* [White Blue][deviant-sample-1]

* [Black Red][deviant-sample-2]

* [White Multicolor][deviant-sample-3]

-- -- --

Selamat Menikmati!


[//]: <> ( -- -- -- links below -- -- -- )

[english-version]:  https://epsi-rns.gitlab.io/design/2016/10/03/inkscape-flat-isometric-wallpaper/

[image-pallete]:        /posts/desain/2016/10-flat/flat-deco-03-accent700.png
[image-dialog-page]:    /posts/desain/2016/10-flat/flat-isometric-dialog-page.png
[image-dialog-grids]:   /posts/desain/2016/10-flat/flat-isometric-dialog-grids.png
[image-dialog-shadow]:  /posts/desain/2016/10-flat/flat-isometric-dialog-shadow.png
[image-dock-layers]:    /posts/desain/2016/10-flat/flat-isometric-dock-layers.png
[image-dock-transform]: /posts/desain/2016/10-flat/flat-isometric-dock-transform.png
[image-snap-handle]:    /posts/desain/2016/10-flat/flat-isometric-snap-handle.png
[image-box-inner]:      /posts/desain/2016/10-flat/flat-isometric-box-inner.png
[image-box-outer]:      /posts/desain/2016/10-flat/flat-isometric-box-outer.png
[image-bar-first]:      /posts/desain/2016/10-flat/flat-isometric-bar-first.png
[image-bar-all]:        /posts/desain/2016/10-flat/flat-isometric-bar-all.png
[image-bar-cross]:      /posts/desain/2016/10-flat/flat-isometric-bar-cross.png
[image-bar-shadow]:     /posts/desain/2016/10-flat/flat-isometric-bar-shadow.png
[image-bar-color]:      /posts/desain/2016/10-flat/flat-isometric-bar-color.png
[image-text-snap]:      /posts/desain/2016/10-flat/flat-isometric-text-snap.png
[image-preview]:        /posts/desain/2016/10-flat/flat-isometric-preview.png
[image-final]:          /posts/desain/2016/10-flat/flat-isometric-final.png
[image-ribbon]:         /posts/desain/2016/10-flat/flat-isometric-ribbon.png

[dotfiles-final]:       /posts/desain/2016/10-flat/flat-isometric-looks.svg.gz

[deviant-sample-1]: http://nurwijayadi.deviantart.com/art/Anies-Sandiaga-Hashtag-646646564
[deviant-sample-2]: http://nurwijayadi.deviantart.com/art/Material-Design-Wallpaper-646576299
[deviant-sample-3]: http://nurwijayadi.deviantart.com/art/Flat-Wallpaper-with-Isometric-Looks-646980074
