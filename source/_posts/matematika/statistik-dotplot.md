---
title     : Statistik - Dotplot
date      : 2020/02/02 09:17:35
tags      : [python]
category  : [matematika]
keywords  : [matplotlib, statistik]

toc       : "toc/2020-matematika"
---

<a name="prakata"></a>

## Prakata

> Tujuan: Menggambar Bagan, Berdasarkan Populasi Data

Misalnya sohib pembaca memiliki suatu data statistik,
mungkin saja sohib bertanya-tanya bagaimana cara untuk menampilkan
data dengan cara yang tepat.
Artikel ini adalah latihan bagi saya,
sebagai pemula di bidang statistik.
Dari pemula, untuk pemula.

Saya menggunakan `python`, sebagai bahasa pemrograman,
di dalam artikel ini.

### Daftar Isi

* [Prakata](#prakata): Daftar Isi

* 1: [Menempatkan Data Acak](#populasi)

* 2: [Grafik Histogram](#histogram-grafik)

* 3: [Teks Histogram](#histogram-teks)

* 4: [Dotplot](#dotplot)

* 5: [Stemplot](#stemplot)

* [Penutup](#penutup)

### Bahasa Inggris

Artikel ini juga disajikan di blog penulis yang lain,
dalam bahasa Inggris:

* [Statistic - Dotplot][english-version]

-- -- --

<a name="populasi"></a>

## 1: Menempatkan Data Acak

> Populasi Data

Supaya contoh ini berjalan dengan baik,
kita membutuhkan contoh data yang dapat dipakai.
Langkah pertama kita adalah mengisi data seperlunya.
Pilihan saya adalah kasus tinggi badan dari siswa dalam sentimeter.
Jangkauan-nya adalah antara `165` sampai dengan `174` sentimeter.

Dalam terminologi `python numpy`,
ketentuan ini dapat ditulis ulang yaitu sebagai
 `np.random.randint(165, 175, size=...)`.
Perhatikan perbedaan `+1` di sini.

Skrip selengkapnya adalah:

{% codeblock lang:python %}
import numpy as np

range_min = 165
range_max = 175

np.random.seed(7)
data = np.random.randint(range_min, range_max, size=32)

data_str = ', '.join(str(x) for x in data)
print('[' + data_str + ']')
{% endcodeblock %}

Hasilnya adalah daftar panjang dari bilangan bulat.

{% codeblock lang:python %}
[169, 174, 171, 168, 168, 172, 172, 174, 172, 173, 174, 173, 172, 171, 169, 165, 172, 165, 172, 171, 168, 170, 173, 173, 172, 170, 165, 165, 167, 173, 174, 171]
{% endcodeblock %}

Sekarang kita dapat menyalin keluaran tersebut,
untuk digunakan di skrip berikutnya.

### Data Statis

> Cek dan ricek.

Mengapa disalin?
Mengapa tidak menggunakan data acak saja?
Mengapa menggunakan data statik?

Karena, saya butuh untuk memeriksa data tersebut.
Misalnya dari skrip ke bagan grafik.
Dalam percobaan ini, saya beberapa kali, harus menghitung secara manual.

Tentu saja nantinya kita dapat bealih ke data acak.
Namun sekarang kita membutuhkan data statis.
Setidaknya sebagai awalan.

-- -- --

<a name="histogram-grafik"></a>

## 2: Grafik Histogram

Sekarang saat yang tepat,
untuk menggunakan populasi data di atas menjadi sesuatu yang bermanfaat.

### Kepala Header

Skrip yang kita gunakan membutuhkan `library` di bawah ini:

{% codeblock lang:python %}
import numpy as np
import matplotlib.pyplot as plt
{% endcodeblock %}

### Data

Coba mulai dengan data

{% codeblock lang:python %}
range_min = 165
range_max = 175

data = np.array([
    169, 174, 171, 168, 168, 172, 172, 174, 
    172, 173, 174, 173, 172, 171, 169, 165, 
    172, 165, 172, 171, 168, 170, 173, 173, 
    172, 170, 165, 165, 167, 173, 174, 171
  ])
{% endcodeblock %}

### Bagan Chart

Coba tampilkan, tafsiran data ke `histogram chart` memakai `matplotlib`.

{% codeblock lang:python %}
bins  = np.arange(range_min, range_max+1)

plt.hist(data, bins=bins,
  facecolor="tab:green", edgecolor="k", linewidth=0.7)

plt.show()
{% endcodeblock %}

![statistic: plain histogram chart][image-02-histogram]

Bagan sudah jadi, namun tidak menjelaskan apapun.
Ini sebabnya kita membutuhkan bagan jenis lain,
yaitu yang bernama `dotplot`.

-- -- --

<a name="histogram-teks"></a>

## 3: Teks Histogram

Sebelum beralih lebih lanjut, kita perlu memahami,
bagaimana cara kerja skrip `python` .

### Header dan Data

Sama seperti sebelumnya.

### Bins

Bagan `dotplot` membutuhkan `histogram` yang ada di `numpy`.
Perhitungan nya berdasarkan `bins` sebagaimana di bawah:

{% codeblock lang:python %}
range_x = np.arange(range_min, range_max)
bins    = np.arange(range_min, range_max+1)

freq, edges = np.histogram(data, bins=bins)

print("range_x: " + str(range_x))
print("freq: " + str(freq))
{% endcodeblock %}

Ujung dari `bins` membutuhkan nilai tambahan `+1`.
Maka sekarang kita mendapatkan jumlah kekerapan frekuensi,
sebagaimana berikut di bawah:.

{% codeblock lang:python %}
range_x: [165 166 167 168 169 170 171 172 173 174]
freq: [4 0 1 3 2 2 4 7 5 4]
{% endcodeblock %}

Untuk menghindari perulangan,
kita dapat menulis variabel peubah,
menggunakan fungsi `slice` yang disediakan `python`.

{% codeblock lang:python %}
bins    = np.arange(range_min, range_max+1)
range_x = bins[:-1]
{% endcodeblock %}

### Zip

Coba bikin `tuple` dari kedua daftar `list`,
dan kemudian tampilkan tafsiran dari `tuple` tersebut,
dalam grafik teks di `command line interface`.

{% codeblock lang:python %}
pairs = zip(range_x, freq)

for key, value in pairs:
  print(key, ' | ', ' '.join(np.repeat('*', value)))
{% endcodeblock %}

Lalu jalankan skrip!
Kita akan mendapatkan teks histogram yang cantique.

{% codeblock lang:python %}
165  |  * * * *
166  |  
167  |  *
168  |  * * *
169  |  * *
170  |  * *
171  |  * * * *
172  |  * * * * * * *
173  |  * * * * *
174  |  * * * *
{% endcodeblock %}

* .

![statistic: horizontal histogram text][image-03-text]

-- -- --

<a name="dotplot"></a>

## 4: Dotplot

Sekali lagi sekarang saat yang tepat,
untuk menggunakan populasi data di atas menjadi sesuatu yang bermanfaat.

Saqya mendapatkan carany dari `stackoverflow`.

* [How to create a dot plot in Matplotlib?][reference-01]

### Header and Data

Sama seperti sebelumnya

### Bagan

Untuk membuat `dotplot`,
kita membutuhkan `scatter chart` yang disediakan oleh `matplotlib`.
Dan `scatter chart` ini membutuhkan fungsi `meshgrid`,
yang disediakan oleh `numpy`.

{% codeblock lang:python %}
bins    = np.arange(range_min, range_max+1)
range_x = bins[:-1]

freq, edges = np.histogram(data, bins=bins)

y = np.arange(1, freq.max()+1, 1)
x = range_x
X,Y = np.meshgrid(x,y)

plt.scatter(X,Y, c=Y<=freq, cmap="Greens")

plt.show()
{% endcodeblock %}

![statistic: plain dotplot chart][image-04-dotplot-01]

### Hiasan Dekorasi

Sekarang kita dapat melengkapi bagan,
dengan `ticks`, `label`, berikut `limits`.
Kita juga dapat menyembunyikan `spines border`.

{% codeblock lang:python %}
bins    = np.arange(range_min, range_max+1)
range_x = bins[:-1]

freq, edges = np.histogram(data, bins=bins)

y = np.arange(1, freq.max()+1, 1)
x = range_x
X,Y = np.meshgrid(x,y)

plt.title('Height of Students')
plt.xlabel('Height (cm)')
plt.ylabel('Frequency')
plt.yticks(y)
plt.xticks(x)
plt.ylim(0, freq.max()+1)
plt.xlim(range_min-3, range_max+2)
plt.tick_params(top=False, bottom=True, left=False, right=False, labelleft=False, labelbottom=True)

for pos in ['right', 'top', 'left']:
    plt.gca().spines[pos].set_visible(False)

plt.scatter(X,Y, c=Y<=freq, cmap="Greens")

plt.subplots_adjust(bottom=0.2)
plt.show()
{% endcodeblock %}

![statistic: dotplot chart with decoration][image-04-dotplot-02]

Bagan `dotplot` inilah yang kita butuhkan.

-- -- --

<a name="stemplots"></a>

## 5: Stemplots

Karena saya penasaran,
saya juga mencoba-coba chart bernama `stemplot`.

Say amendapatkan caranya dari situs `geeksforgeeks`.

* [Stem and Leaf Plots in Python][reference-02]

### Menghitung Frekuensi

Bagan `stemplot` menghitung kekerapan frekuensi,
berbasis dari data yang unik.
Karena itu kita dapat mengabaikan nilai yang jumlah frekuensinya nol.

Tentu saja, kita dapat memaanfaatkan perhitungan sebelumnya.

{% codeblock lang:python %} >}}
uniq = np.unique(np.sort(data))
freq = freq[freq >0]
{% endcodeblock %}

Kalau mau lebih singkat, pakai cara di bawah.

{% codeblock lang:python %}
uniq, freq = np.unique(data, return_counts=True)
{% endcodeblock %}

### Bagan

Sekarang, kita dapat melengkapi bagan, berikut hiasan dekorasinya.

{% codeblock lang:python %}
uniq, freq = np.unique(data, return_counts=True)

plt.title('Height of Students')
plt.xlabel('Frequency')
plt.ylabel('Height (cm)')
plt.xticks(np.arange(1, freq.max()+1, 1))
plt.yticks(np.arange(range_min-1, range_max+1, 1))

for pos in ['right', 'top', 'left']:
    plt.gca().spines[pos].set_visible(False)

plt.ylim(range_min-2, range_max+2)  
plt.xlim(0, freq.max()+1)  
plt.stem(freq, uniq)

plt.subplots_adjust(bottom=0.2)
plt.show()
{% endcodeblock %}

![statistic: stemplot chart][image-05-stemplot]

Sudah jadi, walaupun saya juga belum paham,
apa sebetulnya kegunaan dari `stemplot`.

-- -- --

<a name="penutup"></a>

## Penutup

Gitu aja dah. Makasih yacc, sudah mampir.

Bagaimana menurut sohib?

[//]: <> ( -- -- -- links below -- -- -- )

[english-version]:  https://epsi.bitbucket.io/2020/02/02/statistic-dotplot/

[reference-01]:         https://stackoverflow.com/questions/49703938/how-to-create-a-dot-plot-in-matplotlib-not-a-scatter
[reference-02]:         https://www.geeksforgeeks.org/stem-and-leaf-plots-in-python/

[image-02-histogram]:   /posts/matematika/2020/02/02-histogram.png
[image-03-text]:        /posts/matematika/2020/02/03-text.png
[image-04-dotplot-01]:  /posts/matematika/2020/02/04-dotplot-nodeco.png
[image-04-dotplot-02]:  /posts/matematika/2020/02/04-dotplot-withdeco.png
[image-05-stemplot]:    /posts/matematika/2020/02/05-stemplot.png
