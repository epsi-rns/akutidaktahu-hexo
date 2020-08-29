---
title     : Inkscape - Animasi Cincin
date      : 2017/11/15 09:17:35
tags      : [inkscape]
category  : [desain]
keywords  : [animasi, saporito]

toc       : "toc/2015-inkscape-keseharian"
---

### Prakata

Gagasan membuat animasi cincin ini saya mulai,
setelah mempraktekkan bahan ajar dari Pakde Nick Saporito.

* [Inkscape Tutorial: Vector Progress Rings][saporito]

-- -- --

### Kelam

#### Bahan SVG Terpadu

> Langsung saja yacc

Sumber gambar inkscape dapat sohib unduh di sini:

* [akutidaktahu.netlify.app/.../progress-ring-dark.svg][source-dark]

atau di siniiii

* [akutidaktahu.netlify.app/.../progress-ring-bright.svg][source-bright]

Dan hasilnya seperti ini:

![Progress Ring: Dark][image-dark]

Maksudnya terpadu, adalah semua saya simpan dalam satu berkas saja.
Tidak terpisah-pisah, sehingga mudah mengelolanya.

### DeviantArt

Saya juga menaruh tautan di DeviantArt, dengan SVG yang dapat diunduh.

* [Progress Ring Animation][deviant-ring]

#### Meng-ekstrak Tiap-Tiap Frame

Sudah kubikinkan lapisan `layer` juga untuk masing-masing keperluan,
salah satunya bernama `cut-frame`, yang berguna untuk memilih objek
dan kemudian meng-ekspor tiap frame dengan mudahnya ke berkas `.png`.

![Progress Ring: Select Frame][select-dark]

Seperti terlihat, saat meng-eksport `.png` dari objek yang dipilih,
maka sudah ada nama target-nya, misalnya akan disimpan ke berkas
`/home/epsi/Documents/progress-ring/progress-095.png`.

![Exports and Layers][layers-bright]

#### XML

> Bagaimana caranya?

Nah, kita dapat menggunakan `XML editor` yang tersedia di Inkscape,
untuk menyunting `id`-nya.

![XML Editor][xml-bright]

Atau.... akan lebih mudah lagi kalau mau langsung menynunting,
dengan menggunakan text editor.
Karena dengan text-editor, kita dapat langsung melakukan `find-and-replace`.
Misalnya untuk mengganti pengaturan `dpi`,
atau mengganti nama tempat folder dari target berkas yang akan disimpan.
Cara ini sangat terasa manfaatnya kalau objek-nya sudah banyak.

{% codeblock lang:xml %}
    <rect
       inkscape:export-filename="/home/epsi/Documents/progress-ring/progress-095.png"
       inkscape:export-ydpi="640"
       inkscape:export-xdpi="640"
       ...
       id="95%"
       ...
       />
{% endcodeblock %}

![Editing SVG in Text Editor][editor-bright]

#### Meng-ekstrak Tiap-Tiap Berkas KE PNG

Pilih tiap-tiap objek frame untuk semua cincin, lalu eksport ke `.png`.
Maka nanti sohib akan dapat melihat tiap-tiap frame,
di perambah berkas (`file manager`).

![File Manager: Each Frames][caja-dark]

#### Animasi GIMP

Pertama kali terpikir ntuk membuat animasi,
adalah dengan menggunakan fitur animasi yang disediakan oleh `GIMP`.
Namun setelah di-eksport ke `GIF`, ternyata hasilnya kurang bagus,
karena dari GIF yang dihasilkan , tampaknya ada warna yang hilang.
Sehingga hasilnya tidak halus.

![Progress Ring: GIF Animation][image-gif]

#### FFMPEG

Woke wokeeee...
Gimana cara ngalusinnyah nie sohib?
Ya pakai ffmpeg-lah.

> Langsung saja yacc

Perintahnya radha panjang.
Rincian-nya tolong baca manual sendiri yacc.

{% codeblock lang:bash %}
$ ffmpeg \
    -framerate 4 \
    -pattern_type glob -i '*.png' \
    -c:v libx264 -profile:v baseline \
    -level 3.0 \
    -pix_fmt yuv420p \
    progress-dark.mp4
{% endcodeblock %}

Dan hasilnya adalaaah

  <video width="250" height="250" controls>
    <source src="/posts/desain/2017/11-cincin/progress-dark.mp4" type="video/mp4">
    Cak, browser-mu ijik orak mendukung video.
  </video>

#### Peringatan,

Aku masih gak tau caranya mengatur waktu,
yang berbeda untuk tiap frame dengan `ffmpeg`.
Mengatur `delay` berbeda untuk tiap frame,
sangat mudah dilakkan dengan `gimp`.
Masalahnya memang video berbasis `framerate`,
yang berbeda konsep dengan `delay` di animasi.

-- -- --

### Cerah

#### Bahan SVG Terpadu

> Langsung saja yacc

Sumber gambar inkscape dapat sohib unduh di sini:

* [epsi-rns.gitlab.io/.../progress-ring-bright.svg][source-bright]

Dan hasilnya seperti ini:

![Progress Ring: Bright][image-bright]

Maksudnya terpadu, adalah semua saya simpan dalam satu berkas saja.
Tidak terpisah-pisah, sehingga mudah mengelolanya.


#### Meng-ekstrak Tiap-Tiap Frame

Langkahnya sama bro dengan tampilan `gelap` di atas.

![Progress Ring: Select Frame][select-bright]

#### Meng-ekstrak Tiap-Tiap Berkas KE PNG

Lagi-lagi langkahnya sama bro dengan tampilan `gelap` di atas.

![File Manager: Each Frames][caja-bright]

#### FFMPEG

> Langsung lagi yacc

Perintahnya begini nie sohib

{% codeblock lang:bash %}
$ ffmpeg \
    -framerate 4 \
    -pattern_type glob -i '*.png' \
    -c:v libx264 -profile:v baseline \
    -level 3.0 \
    -pix_fmt yuv420p \
    progress-bright.mp4
{% endcodeblock %}

Dan hasilnya adalaaah

  <video width="250" height="250" controls>
    <source src="/posts/desain/2017/11-cincin/progress-bright.mp4" type="video/mp4">
    Cak, browser-mu ijik orak mendukung video.
  </video>

-- -- --

### Penghalusan

Karena penulis sukanya yang halus-halus dan bening-bening.

#### Bahan SVG Terpadu

Semua frame dapat ditunjukkan di sini:

![Progress Ring: Bright][image-smooth]

#### Tahapan Penghalusan Busur

> Gimana caranya biar klimis?

Ditarok saja lapisan di atasnya secara `overlay`,
busur lain di atas bususr yang ada.

**Normal Arc**

Busur cerah yang normal penampakannya seperti ini.

![Normal Arc][045-bright]

**Overlay Arc**

Lapisan busur yang bening, ditaruh di atasnya.

![Overlay Arc][045-add]

**Smooth Bright**

Maka... tadaaa.. hasil akhirnya lumayan khaaan.

![Smooth Arc][045-smooth]

#### Busur Overlay

> Mulai dari warna solid, lalu dibikin bening

Seperti biasa, pakailah gradien dengan warna RGBA,
untuk mengatur masing-masing warna stroke.

![Overlay Arc: Gradient][045-gradient]

* simpul atas: bebas warnanya, toh gak keliatan

* simpul tengah: sama dengan warna gambar latar,
  misalnya `#f5f5f5ff`.

* simpul bawah: sama dengan gradien bawah dari warna busur normal,
  misalnya as `#ffeb3bff`.
  Bedanya, warna `alpha` harus di-nolkan supaya bening tembus cahaya.
  Untuk contoh warna di atas menjadi `#ffeb3b00`.
  
#### Membenahi Outline

Kalau diperhatikan, di busur ini ada `outline` yang mengganggu,
Ini terjadi karena di bawah ada objek berwarna.

![Overlay Arc: Annoying Outline][045-outline]

Sohib dapat membenahi ini dengan menambahkan panjang busur,
dengan panjang yang sangat tipis.
Yaitu dengan mengubah `sodipodi:start`, dari `0` ke `-0.01`.
Penyuntingan dapat langsung dilakukan dengan XML editor.

![Overlay Arc: Change start XML Editor][045-xml]

Tentunya, sohib perlu juga mengubah warna dari simpul gradien yang atas,
ke warna stroke yang sama dengan gambar latar, misalnya `#f5f5f5ff`.

Mestinya sekarang sohib sudah mendapatkan busur yang halus.

![Overlay Arc: Fix Outline][045-outline-f]

#### FFMPEG

Langsung hasilnya saja ycc sohib:

  <video width="250" height="250" controls>
    <source src="/posts/desain/2017/11-cincin/progress-bright-smooth.mp4" type="video/mp4">
    Cak, browser-mu ijik orak mendukung video.
  </video>

Untuk saat ini, hasilnya belum bermanfaat untuk kegiatan penulis.
Aku akan pakai suatu hari, karena di sekitar tahun 2020,
aku perlu membikin beberapa presentasi.

-- -- --

### Kdenlive

Sohib juga dapat menggunakan transparansi,
lalu dibikin berkas `.png`,
untuk kemudian dipakai ke dalam `kdenlive`,
untuk membikin semacam `watermark`.

#### Lini Masa

Mudah koq untuk menambahkan segerobak gambar,
untuk dijadikan frame di lini masa `kdenlive`.

![Transparent Watermark in Video using Kdenlive][kdenlive-line]

YAng bikin repot itu, saat haru melakukan pengaturan berulang,
misalnya mengubah durasi untuk tiap-tiap gambar

#### XML

Kalau sohib pikir menyunting durasi gambar membosankan,
sebetulnya akan lebih mudah untuk menyunting berkas `*.kdenlive`
dengan menggunakan text editor.
Lalu ganti semua keberadaan dari properti `length`,
dari lima detik ke satu detik, 
atau tepatnya dari `00:00:05.000` ke `00:00:01.000`.

{% codeblock lang:xml %}
 <producer id="producer2" in="00:00:00.000" out="00:00:00.960">
  <property name="length">00:00:01.000</property>
  <property name="eof">pause</property>
  <property name="resource">/home/epsi/Documents/progress-ring/progress-005.png</property>
  ...
 </producer>
{% endcodeblock %}

![Editing Kdenlive in Text Editor][kdenlive-text]

#### FFMPEG

Hasil `render` dari `kdenlive` ukuran-nya besar,
dan akan menyebalkan kalau kita mengirim berkas yang besar 
ke teman kita di whatsapp atau telegram.
Namun tidak masalah kalau menggunakan:
facebook atau twitter atau instagram.
Kita dapat mengurangi ukuran dengan `ffmpeg`.

{% codeblock lang:bash %}
$ ffmpeg -i test-bengkel-shadow.mp4 \
 -an \
    test-bengkel-fourth-shadow.mp4
{% endcodeblock %}

#### Hasil Video MP4

  <video width="360" height="270" controls>
    <source src="/posts/desain/2017/11-cincin/bengkel-fourth-shadow.mp4" type="video/mp4">
    Cak, browser-mu ijik orak mendukung video.
  </video>

-- -- --

Gitu aja dah.

Makasih yacc, sudah mampir.


[//]: <> ( -- -- -- links below -- -- -- )

[saporito]: https://www.youtube.com/watch?v=zu0HpnH1dXo

[image-gif]:    /posts/desain/2017/11-cincin/progress-ring-all.gif

[image-dark]:   /posts/desain/2017/11-cincin/progress-ring-dark.png
[select-dark]:  /posts/desain/2017/11-cincin/select-dark.png
[caja-dark]:    /posts/desain/2017/11-cincin/file-manager-dark.png
[source-dark]:  /posts/desain/2017/11-cincin/progress-ring-dark.svg

[image-bright]: /posts/desain/2017/11-cincin/progress-ring-bright.png
[select-bright]:/posts/desain/2017/11-cincin/select-bright.png
[layers-bright]:/posts/desain/2017/11-cincin/layers-bright.png
[xml-bright]:   /posts/desain/2017/11-cincin/xml-bright.png
[editor-bright]:/posts/desain/2017/11-cincin/editor-bright.png
[caja-bright]:  /posts/desain/2017/11-cincin/file-manager-bright.png
[source-bright]:/posts/desain/2017/11-cincin/progress-ring-bright.svg

[045-bright]:   /posts/desain/2017/11-cincin/progress-045-normal-s.png
[045-smooth]:   /posts/desain/2017/11-cincin/progress-045-smooth-s.png
[045-add]:      /posts/desain/2017/11-cincin/progress-045-additional-s.png
[045-gradient]: /posts/desain/2017/11-cincin/progress-045-gradient-s.png
[045-outline]:  /posts/desain/2017/11-cincin/progress-045-outline-crop.png
[045-outline-f]:/posts/desain/2017/11-cincin/progress-045-outline-fix.png
[045-xml]:      /posts/desain/2017/11-cincin/progress-045-xml.png

[image-smooth]: /posts/desain/2017/11-cincin/progress-bright-smooth.png

[deviant-ring]: https://www.deviantart.com/nurwijayadi/art/Progress-Ring-Animation-713895798

[kdenlive-line]:/posts/desain/2017/11-cincin/kdenlive-timeline.png

[kdenlive-text]:/posts/desain/2017/11-cincin/editor-kdenlive.png
