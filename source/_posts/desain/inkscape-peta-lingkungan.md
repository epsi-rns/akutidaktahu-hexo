---
title     : Inkscape - Peta Lingkungan
date      : 2020/08/24 09:17:35
tags      : [inkscape, lingkungan]
category  : [desain]
keywords  : [RT/RW, Rukun Warga, Rukun Tetangga]

toc       : "toc/2015-keseharian"
---

### Prakata

Inkscape bukan saja dipakai untuk membuat
sesuatu karya seni yang cantique,
namun juga dipakai untuk kegiatan sehari-hari.

__diagramming adalah bagian dari keseharian__

Berikut artikel yang __mediocre__ yang biasa saja,
mengenai penggunaan __inkscape__ untuk sehari-hari,
karena aku bisanya cuma itu... hehehe 🤦🏻‍♂️.
Aku belum bisa bikin karya yang cantique menarique.

#### Musrenbang

Semenjak tahun 2018,
saya menjadi pendamping RW (rukun warga) di musrenbang DKI.
Tiap tahun ada saja tugas berdiskusi dengan para RT (Rukun Tetangga),
dan diskusi ini juga membutuhkan peta `map`. 
Biasanya sih, saya tidak mau repot dan merepotkan,
pakai google map saja, di screenshot, lalu cetak pakai printer,
berikan ke tiap-tiap ketua RT untuk dicorat-coret,
lalu saat koempoel di pos RW,
ya disiapkan lagi lembaran untuk dicorat-coret.
Begitu saja koq repot!

Waktu berlalu begitu cepat,
dan gedung kelurahan yang reot dan super sumuk-pun,
akhirnya berganti gedung megah.
Begitu pula RW-06 tercinta ini akhirnya punya tempat sendiri,
yang dapat dijadikan kantor.
Maka kubikinkanlah peta yang cantique,
supaya tidak kalah dengan RW lain yang sudah punya peta duluan.

Setidaknya kalau ada musrenbang lagi,
saya sudah punya peta untuk dicetak,
yang bisa saya atur sendiri isinya.
Dapat ditambahkan lokasi lampu jalan mana saja remang-remang,
atau keterangan saluran air mana saja yang banjir.
Pokoke RW in lebih siap akhir tahun ini.

#### Source SVG

Monggo (kang)mas. Mangga a(kang). Silahkan tu(kang).
Langsung saja unduh di sini.

* [akutidaktahu.netlify.app/.../rw-06.svg][source-svg]

#### Acuan

Ya guglemap dunk...
Mosok mau kek jaman bahuela, ngukur jalan pakai meteran?

Caranya yacc....
Tinggal skrinsut, crop pakai `gimp` supaya yang muncul cuman RW-06 saja.
lalu ditaruh ke dalam inkscape, ke dalam lapisan `layer` tersendiri.

![Peta RW: mbah guglemap][image-gugelmap]

Ukuran kertas juga bebas-bebas saja,
aku pakai (cieee... aku..) ukuran lebar 500px x kali 600px.
Kalo nanti kurang, khan bisa ditambahin ukurannya.

> Gampang toh.

#### Alternatif

Ada cara lain selain yang diungkap di artikel ini,
yaitu unduh SVG dari `openstreemap`.
Lebih rinci. Silahkan dicoba sendiri. Bagus koq.

![Open Street Map][openstreetmap]

Sayangnya SVG tersebut tidak dipisahkan berdasarkan lapisan `layer`.

#### Sketsa Jalan

Hayuk kita bikin lapisan `layer` nya dulu,
lalu kita bikin jalan, kali sungai, berikut taman atau jalur hijau.
Semuanya di atas gugel map yang sudah kita bikin tadi.

![Peta RW: Sketsa Jalan][image-sketsa]

Nah soal jalan, ada jalan utama, jalan rumah,
jalan gang, di-kira-kira saja.
Tiap RW juga berbeda kebutuhan peta-nya.
Pokoke bikin dulu, gak usah bagus-bagus.
Ntar khan bisa diperbaiki

Jangan lupa, nama jalan ditaruh di lapisan layer yang berbeda.

#### Lahan Warga

Ada beberapa tahap.

1. Gandakan lapisan `layer` jalan di atas.
   Lalu sembunyikan sementara, lapisan `layer` jalan tadi.

2. Kemudian di lapisan `layer` yang baru,
   lakukan `path - union` supaya semua jalan jadi satu.

3. Bikin kota baru memenuhi seluruh halaman,
   misalnya ukuran lebar 500px x kali 600px.

4. Lakukan `path - difference` antara jalan dengan kotak tadi,
   dengan posisi kotak di atas-nya.

![Peta RW: Lahan Warga Setempat][image-lahan]

5. Lakukan `break apart`, lalu hapus yang tidak perlu.
   Buang saja. Jangan disimpan.

6. Beri nama RT seperlunya.
   Tentunya dengan lapisan `layer` tersendiri.

![Peta RW: Sederhana][image-sederhana]

Sekarang sohib sudah punya peta yang sederhana

#### Lapisan Layer

Sejauh ini kita sudah punya lapisan `layer` yang cukup banyak.

![Peta RW: Lapisan Layer Awal][image-lapisan-04]

#### Menghias

Nah ini, baru inkscape-nya terpakai.

1. Group seluruh jalan, lalu `filter - drop shadow`,
   supaya ada bayangan.

2. Nama jalan diberi warna berbeda.
   Ini mudah kalau memakai pallete materialize color.
   Gradasinya sudah disiapkan.

3. Tiap RT (rukun tetangga),
   juga diberi warna berbeda.

![Peta RW: Menghias dengan Bayangan dan Warna][image-bayangan]

Tampak khan bedanyaaaa...

Nah sekarang, waktunya pamer ke pak RW,
sambil menunggu revisi.

#### Revisi

Ternyata memang revisi sih.
Nama jalan yang diberikan google, ada yang tidak sesuai.
Selera warna juga berbeda.
Dan tiap RT perlu kontras dengan warna berbeda.
Dan teryata aku juga lupa membikin jalan gang, hehe..
Harap maklum orang sok sibuk.

Perubahan yang paling berasa adalah perlunya batas gang dengan RW lain,
sehingga perlu peta `map` yang lebih luas.
Maka ukuran peta perlu diubah menjadi ukuran lebar 600px x kali 600px.
Lebarnya saja diubah.

![Peta RW: Perminatan Revisi dari pak RW][image-revisi]

Jangan lupa lokasi kantor baru RW yacc.

#### Alternatif

> Sudah jadi.

Walaupun hasil akhir sudah terlanjur dibikin dan disetujui
tidak ada salahnya kita melakukan beberapa percobaan,
untuk melihat beberapa lternatif perbaikan.

![Peta RW: Lapisan Layer Akhir][image-lapisan-07]

Misalnya, mentang-mentang ini bulan agustus,
kita bisa saja bikin edisi merah putih.
Sederhana seringkali lebih mengena.
Dengan begini, lokasi kantor RW (Rukun Warga), lebih nampak.

![Peta RW: Edisi Merah Putih][image-bendera]

Atau seperti biasa bersikeras,
dengan warna kesukaan yang bikin. Hehe...

![Peta RW: Warna Kesukaan][image-kesukaan]

#### Lingkungan Sohib

> Bagaimana Lingkungan Sohib?

Sekarang terserah sohib pembaca nih.
Mau bikin yang kek gimana.
Terserah saja, yang penting sohib berbuat sesuatu,
ke lingkungan setempat.
Dan bentuknya tidak harus menggambar peta.

-- -- --

Itu saja yacc sohib. Sampai jumpaaaaa...

[//]: <> ( -- -- -- links below -- -- -- )

[source-svg]:       /posts/desain/2020/08-map/rw-06.svg
[image-gugelmap]:   /posts/desain/2020/08-map/01-gugelmap.png
[image-sketsa]:     /posts/desain/2020/08-map/02-sketsa.png
[image-lahan]:      /posts/desain/2020/08-map/03-lahan-warga.png
[image-sederhana]:  /posts/desain/2020/08-map/04-peta-sederhana.png
[image-lapisan-04]: /posts/desain/2020/08-map/04-lapisan-layers.png
[image-bayangan]:   /posts/desain/2020/08-map/05-bayangan.png
[image-revisi]:     /posts/desain/2020/08-map/06-revisi.png
[image-lapisan-07]: /posts/desain/2020/08-map/07-lapisan-layers.png
[image-bendera]:    /posts/desain/2020/08-map/07-merah-putih.png
[image-kesukaan]:   /posts/desain/2020/08-map/07-kesukaan.png
[openstreetmap]:    /posts/desain/2020/08-map/openstreetmap.png
