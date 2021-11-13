# basic-informatics (Python) #1

### <span style="color:blue">Tugas #1: Pasfoto Praktikan &#8594; 15 poin</span>
Untuk menyisipkan suatu gambar di dalam dokumen Jupyter Notebook, ukuran gambar menjadi sesuatu yang perlu diperhatikan  agar hasil penyisipan tidak terkesan terlalu kecil atau telalu besar dibandingkan bidang tampilan dokumen. Sebagai acuan umum, panjang dan/atau lebar gambar sebaiknya sekitar 300 piksel.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, sisipkan pasfoto diri anda dengan memperhatikan:
- ukuran pasfoto telah disesuaikan agar terlihat sesuai dengan bidang tampilan dokumen;
- berkas pasfoto telah diletakkan dalam folder/direktori yang sama dengan dokumen laporan ini.
---
![description](filename.png)
---

### <span style="color:blue">Tugas #2: Rumus Matematika &#8594; 20 poin</span>
Dengan dukungan bahasa _markup_ $\LaTeX$, _Markdown_ dapat dipakai untuk menampilkan rumus matematika secara tepat dan rapi. Setiap rumus ditulis di antara sepasang tanda-dollar `$ $`. Beberapa contoh penulisan komponen rumus matematika:

Komponen | ditulis | terlihat
-|:-:|:-:
pangkat   | `$ x^2 $`   | $x^2$
indeks    | `$ p_{akhir} $` | $p_{akhir}$
simbol perkalian | `$ \times $` | $\times$
simbol plus-minus | `$ \pm $` | $\pm$ 
akar kuadrat | `$ \sqrt{16} $` | $\sqrt{16}$
pembagian | `$ \frac{10}{s - 7} $` | $\frac{10}{s - 7}$

<span style="color:red">&#9881;</span> Pada sel di bawah ini tuliskan rumus matematika untuk menentukan akar-akar dari suatu persamaan kuadrat (kerap disebut sebagai "Rumus ABC"): $$ A \, x^2 + B \, x + C = 0 $$
---
x=$\frac{-b{\pm{\sqrt{b^2 -4 \times a \times c}}}}{2 \times a}$
---

### <span style="color:blue">Tugas #3: Berusia Panjang? &#8594; 25 poin</span>
Dapatkah seorang bayi yang baru lahir diharapkah akan hidup terus selama satu milyar ($10^9$) detik?
__Petunjuk__: Lakukan konversi satuan waktu sehingga memudahkan untuk menentukan kelayakan dapat hidup terus dari bayi tersebut.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah suatu program Python lengkap yang melakukan perhitungan untuk menjawab pertanyaan di atas.
---
#var hidup bayi
HidupBayi=10**9

#var konversi waktu
HarapanHari=HidupBayi/86400 
HarapanBulan=HidupBayi/2678400
HarapanTahun=HidupBayi/31536000

#hasil konversi
print('Harapan hidup bayi')
print(HidupBayi, 'detik')
print(HarapanHari, 'hari')
print(HarapanBulan, 'bulan')
print(HarapanTahun, 'tahun')
---
