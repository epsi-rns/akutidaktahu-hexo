---
title     : LaTeX - Rumus Matematika
date      : 2020/01/10 09:17:35
tags      : [latex]
category  : [matematika]
keywords  : [rumus]

toc       : "toc/2020-matematika"

mathjax   : true
---

### Prakata

> Tujuan: Menulis Rumus Matematika dengan LaTeX.

#### Akibat Kurang Bergaul

Beberapa kali saya berharap,
seseorang memperkenalkan LaTeX ke saya,
pada saat kuliah di kampus Teknik dahulu.
Daripada saya berkeluh kesah,
lebih baik saya saja yang memperkenalkan LaTeX kepada sohib sekalian.
Supaya sohib dapat menggunakan LaTeX untuk keperluan sehari-hari,
mulai dari sekedar menulis tugas sekolah,
sampai dengan memgkomunikasikan gagasan di sosial media.

$$ \lim\limits_{x \to \infty} \exp(-x) = x $$

#### Bahasa Inggris

Artikel ini juga disajikan di blog penulis yang lain,
dalam bahasa Inggris:

* [LaTeX - Math Formula][english-version]

-- -- --

### Berdiri Sendiri

Dengan maraknya `data science` dan `pemrograman fungsional`.
Sekarang saya merasa perlu menulis rumus di blog dengan MathJax,
dan juga mengirim rumus ke telegram atau whatsapp dalam format `PNG`.

> Lalu apa masalahnya?

Saya menggunakan `LaTeX` untuk menulis PDF,
dengan hasil keluaran berupa lembaran halaman,
yang selalu berupa halaman besar.
Saya tidak pernah menggunakan `LaTeX`,
untuk membuat gambar berukuran kecil yang berdiri sendiri.
Kalaupun dapat dilakukan, hasilnya selalu tidak pas,
dengan ukuran rumus tersebut.
Hasilnya selalu berupa satu halaman penuh, bahkan untuk rumus pendek.

Untungnya kata berdiri sendiri `standalone`,
cukup membantu untuk menemukan jawabannya saat melakukan googling,
atau duckduckgoing.
Maka sekarang saya mendapatkan hasil keluaran,
yang hanya berisi rumus pendek saja.

{% codeblock lang:latex %}
\documentclass{standalone}
\begin{document}
  {\Large
    $\displaystyle
      \lim\limits_{x \to \infty} \exp(-x) = x
    $
  }
\end{document}
{% endcodeblock %}

Lalu jalankan perintah ini:

{% codeblock lang:bash %}
❯ latex equation.tex
❯ dvipng equation.dvi
❯ feh equation1.png
{% endcodeblock %}

Makan akan muncul penampakan semacam ini:

![LaTeX: Result][image-latex-01]

Kurang bagus?
Bagaimana kalau dihias?

{% codeblock lang:bash %}
❯ dvipng equation.dvi -D 200
❯ convert -border 20x20 -bordercolor white math-051.png math-052.png
❯ feh equation2.png
{% endcodeblock %}

Sekarang sohib dapat melihat penampakan lain sebagaimana di bawah:

![LaTeX: Result][image-latex-02]

Kalau tampilannya mau keren,
sohib dapat menampilkan source-nya di ViM.

![LaTeX: Source and PNG Result][image-ss-vim]

Sohib juga dapat membikin latar gambar,
menjadi bening transparan dengan `dvipng`.

{% codeblock lang:bash %}
❯ dvipng equation.dvi -D 200 -bg transparent
{% endcodeblock %}


-- -- --

### Pemasangan

Bisa jadi sohib membutuhkan paket tambahan,
tergantung sistem yang dipakai.

#### Gentoo

{% codeblock lang:bash %}
❯ sudo emerge -av texlive-latex
❯ sudo emerge -av dvisvgm
❯ sudo emerge -av texlive-latexextra
{% endcodeblock %}

#### openSUSE

Seru nie, akan dipasang 2148 paket tambahan,
kalau menggunakan openSUSE 15.1.

{% codeblock lang:bash %}
❯ sudo zypper install texlive-latex-bin-bin
❯ sudo zypper install texlive-standalone
{% endcodeblock %}

Kalau memerlukan paket tertentu misalnya `cases`,
sohib dapat menambahkan:

{% codeblock lang:bash %}
❯ sudo zypper install texlive-cases
{% endcodeblock %}

-- -- --

### Merapikan Posisi Rumus Dengan Banyak Baris

Setelah beberapa kali percobaan, dan beberapa kali gagal,
Saya berhasil menemukan cara untuk menyamakan posisi,
dari beberapa rumus sekaligus.
Tentunya semuanya dalam satu kestuan berkas yang berdiri sendiri.

#### Masalah Indentasi

{% codeblock lang:latex %}
\documentclass[
  preview
]{standalone}

\usepackage{amsmath}

\begin{document}
\begin{equation*}
\begin{split}
\nonumber 
f(x) &= \frac{5x + 6}{4}\\
     &= \frac{5x + 6}{4}\\
\end{split}
\end{equation*}
\end{document}
{% endcodeblock %}

Seperti yang sohib lihat,
gambar ini memiliki batas pinggir yang tidak diinginkan.

![LaTeX: Multiline Issue][image-latex-03]

#### Bagaimana Penyelesaiannya?

Atur saja indentasinya ke nol.

{% codeblock lang:latex %}
:::latex
\usepackage[fleqn]{amsmath}
\setlength{\mathindent}{0cm}
{% endcodeblock %}

#### Contoh

{% codeblock lang:latex %}
\documentclass[
  preview
]{standalone}

\usepackage[fleqn]{amsmath}
\setlength{\mathindent}{0cm}

\usepackage{amssymb}

\begin{document}
\begin{equation*}
\begin{split}
\nonumber 
      && f(x) = \frac{2x}{4x - 7},
          x \ne \frac{7}{4}\\
\Rightarrow &&         y &= \frac{2x}{4x - 7}\\
\Rightarrow &&  4xy - 7y &= 2x\\
\Rightarrow &&  4xy - 2x &= 7y\\
\Rightarrow && x(4y - 2) &= 7y\\
\Rightarrow &&         x &= \frac{7y}{4y - 2}\\
\therefore
 && f(x)^{-1} = \frac{7x}{4x - 2},
          x \ne \frac{1}{2}\\
\end{split}
\end{equation*}
\end{document}
{% endcodeblock %}

![LaTeX: Multiline Result][image-latex-04]

- -- --

### Saya masih cupu?

> Pertanyaan Umum

Duh, aku khan bukan `coder`?
Bagaimana memulai belajarnya bang?

#### Tea Inside

Bagi orang awam,
cara termudah untuk membikin LaTeX adalah menggunakan TeaLaTeX compiler,
yang dibikin oleh pemuda berbakat bernama **Ammar Faizi** (orang kita).

* [latex.teainside.org/](https://latex.teainside.org/)

Coba saja beberapa rumus `LaTeX`,
dan situs ini akan menyusun hasilnya untuk sohib.

#### Kode Sumber

> Pertanyaan Lagi

Bagaimana mengenai kode sumber?
Aku khan tidak punya `linux ricing` yang keren,
untuk menampilkan hasil yang cantique menarique?

Nah, sohib dapat menggunakan [carbon.now.sh](https://carbon.now.sh/).
Taruh koding-an ke situ, dan sim-salabim.

![LaTeX Source: carbon.now.sh result][image-carbon]

-- -- --

### Kesimpulan

Penulis paham kalau artikel ini pendek.
Karena memang ditujukan sebagai,
dasar pengenalan yang sangat awal ke `LaTeX`.

Sepertinya cukup sekian.
Ini artikel pertama saya di bulan Januari tahun 2020
Artikel pendek yang mungkin akan punya menjadi penting bagi saya.
Karena saya berencana menggunakan banyak `LaTeX`, suatu saat nanti.
Maka perlu ditulis di sini, supaya mudah ditemukan kembali caranya.

-- -- --

LaTeX itu gampang koq.
Hayuuks, kita mainan LaTeX. Hehe..

Kira2 bagaimana sohib?

[//]: <> ( -- -- -- links below -- -- -- )

[english-version]:  https://epsi.bitbucket.io/2020/01/10/latex-math-formula/

[image-latex-01]:   /posts/matematika/2020/01/latex-limit-01.png
[image-latex-02]:   /posts/matematika/2020/01/latex-limit-02.png
[image-latex-03]:   /posts/matematika/2020/01/multiline-03.png
[image-latex-04]:   /posts/matematika/2020/01/multiline-04.png
[image-ss-vim]:     /posts/matematika/2020/01/vim-latex-formula.png
[image-carbon]:     /posts/matematika/2020/01/carbon-latex.png
