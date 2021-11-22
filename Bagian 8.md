# basic-informatics (Python) #8


### <span style="color:blue">Tugas #1: Diagram Lintasan Bola &#8594; 20 poin</span>

Bola yang dilemparkan dengan kecepatan awal $v_0$ (m/s) pada arah sudut $\theta$ (rad) terhadap sumbu-$x$ (sumbu mendatar) akan membuat lintasan $y$ (m) yang mengalami perubahan sebagai fungsi $x$ sesuai Persamaan $(1)$:

$$ y = f(x) = x \, \tan{\theta} - \frac{1}{2 \, v_0^2} \, \frac{g \, x^2}{(\cos{\theta})^2} + y_0 \quad\quad\quad (1) $$

dengan

- $x$ adalah perubahan jarak bola secara mendatar (m);
- $g$ adalah percepatan gravitasi ($g = 9.81$ m/s$^2$) dan
- $(0, y_0)$ adalah posisi awal bola (m).

<span style="color:red">&#9881;</span> Pada sel di bawah ini, dengan memanfaatkan pustaka `numpy` dan `matplotlib`, tulislah program Python <b>lengkap</b> bernama `LintasanBola.py` yang menampilkan kurva lintasan bola sesuai Persamaan $(1)$ untuk $y \geq 0$. Mula-mula masukkan dulu jawaban pengguna program melalui papan-ketik (<i>keyboard</i>) terkait pertanyaan:

- $y_0$ = posisi tegak bola pada keadaan awal;
- $\theta$ = sudut arah bola dilemparkan pada keadaan awal dan
- $v_0$ = laju awal bola ketika dilemparkan.

Grafik yang memuat kurva lintasan bola tersebut seharusnya dilengkapi dengan dekorasi berupa judul grafik, label dari sumbu-$x$ dan sumbu-$y$, serta batas-batas sumbu sehingga lintasan terlihat secara lengkap dan jelas. Setelah grafik ditampilkan pada layar komputer, simpankan grafik tersebut ke dalam berkas bernama `LintasanBola.pdf`.

<b>Petunjuk</b>: Sertakan berkas grafik `LintasanBola.pdf` buatan anda bersama berkas ber-ekstensi: .ipynb hasil dari Laporan Lab PDI-08 ketika anda melakukan <i>submission</i> praktikum ini.
```
#LintasanBola.py: Program yang menampilkan kurva lintasan bola sesuai Persamaan  (1)  untuk  𝑦≥0 
#                 Finandi 11/11/2021


# Menampilkan judul program
print('LintasanBola.py')
print('---------------')

# Memangil Pustaka
import numpy as np
import matplotlib.pyplot as plt
from math import *

# Membuat program masukan dan variable
y0 = float(input('Masukkan posisi tegak bola pada keadaan awal:'))
theta = float(input('Masukkan sudut arah bola dilemparkan pada keadaan awal:'))
v0 = float(input('Masukkan laju awal bola ketika dilemparkan (m/s):'))
g = 9.81 #m/s**2

# Melakukan definisi fungsi
def f(x):
    y = x*tan(theta) - 1/(2*v0**2)* (g*x**2)/(cos(theta)**2) + y0
    return y

# Membuat batas untuk x dimulai dari 0 untuk selanjutnya dilakukan iterasi; 𝑦≥0
i = 0
while True:
    if f(i) >= 0:
        i += 0.001   # Rentang dibuat kecil agar akurat
    else:
        break

# Membuat larik
n = int(input('batas nilai pada sumbu-x:'))
x = np.linspace(0,i,n)

# Melakukan vektorisasi
y = f(x)

# Membuat grafik
grafik = plt.figure()
plt.plot(x,y)
plt.xlabel('x')
plt.ylabel('y')
plt.legend(['lintasan perubahan bola'])
plt.grid()
# Menampilkan grafik
plt.show()

# Menyimpan grafik kedalam berkas PDF 
grafik.savefig('LintasanBola.pdf')
```


### <span style="color:blue">Tugas #2: Grafik dari Data &#8594; 25 poin</span>

Untuk menjajagi bentuk dan sebaran data yang tersimpan di dalam suatu berkas teks, acapkali ditempuh langkah pertama berupa menampilkan grafik dari data tersebut. Setelah grafik data terlihat jelas barulah dapat ditentukan langkah analisis selanjutnya.

Contoh berkas teks yang berisikan data berbentuk dua kolom adalah berkas `xy.dat` yang menyertai Laporan Lab ini. Sebagian awal dari isi berkas ini adalah seperti berikut:

<center><img src="xy.png"></center>

Sesuai dengan nama berkasnya, nilai-nilai pada kolom kiri dan kolom kanan masing-masing adalah koordinat-$x$ dan koordinat-$y$ dari suatu kurva.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, dengan memanfaatkan pustaka `numpy` dan `matplotlib`, tulislah program Python <b>lengkap</b> bernama `Baca2Kolom.py` yang membaca, menampilkan kurva dari dan mengolah data dua-kolom yang tersimpan di dalam berkas `xy.dat`.

- Mula-mula, baca berkas sehingga nilai-nilai pada kolom kiri tersimpan pada `listX` dan nilai-nilai pada kolom kanan tersimpan pada `listY`.
- Ubah masing-masing kedua <i>lists</i> tersebut menjadi dua bentuk larik (<i>array</i>) `x` dan `y` yang sesuai dengan pustaka `numpy`.
- Tampilkan grafik (beserta dekorasinya yang lengkap) yang memuat kurva `x` vs `y`.
- Hitung dan tampilkan nilai terkecil, nilai terbesar,  nilai rerata (<i>mean</i>) dan simpangan baku (<i>standard deviation</i> dari larik `y`.

<b>Petunjuk</b>: Pelajari dan gunakan fungsi-fungsi berikut yang disediakan pustaka `numpy`: `amin()`, `amax()`, `mean()` dan `std()`.
```
#Baca2Kolom.py: Program yang membaca, menampilkan kurva dari dan mengolah 
#               data dua-kolom yang tersimpan di dalam berkas xy.dat.
#               Finandi 11/11/2021


# Menampilkan judul program
print('Baca2Kolom.py')
print('-------------')

# Memanggil pustaka
import numpy as np
import matplotlib.pyplot as plt
from math import *

# Membuka dan membaca berkas
baca = open('xy.dat','r')
baris = baca.readlines()

# Mengubah list menjadi larik
listX = [] 
listY = []
for i in range (len(baris)):
    kata = baris[i].split()
    listX.append(float(kata[0]))
    listY.append(float(kata[1]))
# Mengubah ist to array
x = np.array(listX) # larik x
y = np.array(listY) # larik y

# Membuat grafik
grafik = plt.figure()
plt.plot(x,y)
plt.title('Grafik x vs y')
plt.xlabel('x')
plt.ylabel('y')
plt.grid()
# Menampilkan grafik
plt.show()

# Menghitung nilai terkeceil, terbesar, rerata, dan simpangan baku dari larik y
print('Nilai Terkecil:', np.amin(y))
print('Nilai Terbesar:', np.amax(y))
print('Rerata(mean):%5.3f' %np.mean(y))
print('Simpangan Baku(std):%5.3f' %np.std(y))
```


### <span style="color:blue">Tugas #3: Fungsi Rapat Kementakan &#8594; 30 poin</span>

Pada kehidupan sehari-hari, banyak peristiwa di alam terjadi dengan frekuensi relatif yang dapat dilukiskan sebagai fungsi rapat kementakan (<i>probability density function</i>) normal. Fungsi ini memiliki bentuk kurva yang khas, yakni mirip bentuk genta atau stupa. Bentuk spesifik dari fungsi ini tergantung pada dua parameter: nilai rerata (<i>mean</i>) $\mu$ dan simpangan baku (<i>standard deviation</i>) $\sigma$. Nilai rerata menentukan kecenderungan memusat dari fungsi ini sedangkan simpangan baku menentukan kecenderungannya untuk menyebar. Untuk sejumlah nilai variabel mandiri $x$, fungsi rapat kementakan normal menimbulkan sejumlah nilai $y$ terkait yang dihubungkan dengan rumus:

$$ y(x) = \frac{1}{\sigma \, \sqrt{2 \, \pi}} \, e^{-\frac{1}{2} \left[ \frac{x - \mu}{\sigma} \right]^2} \quad\quad\quad (2) $$

dengan $e$ = 2.71828 dan $\pi$ = 3.141594.

Grafik berikut menampilkan empat bentuk fungsi rapat kementakan normal pada rentang $x$ yang sama namun dengan nilai $\mu$ dan $\sigma$ yang berbeda-beda:
<p>
<center><img src="normal.png"></center>

<span style="color:red">&#9881;</span> Pada sel di bawah ini, dengan memanfaatkan pustaka `numpy` dan `matplotlib`, tulislah program Python <b>lengkap</b> bernama `KurvaNormal.py` yang menggambar-ulang grafik dengan empat kurva fungsi rapat kementakan normal di atas secara semirip mungkin. Gunakan Persamaan $(2)$ untuk membangkitkan pasangan nilai-nilai $(x, y)$ yang diperlukan. Selain tampilan dari grafik pada layar komputer, simpankan juga grafik tersebut ke dalam berkas bernama `KurvaNormal.png`. 

<b>Petunjuk</b>: Sertakan berkas grafik `KurvaNormal.png` buatan anda bersama berkas ber-ekstensi: .ipynb hasil dari Laporan Lab PDI-08 ketika anda melakukan <i>submission</i> praktikum ini.
```
#KurvaNormal.py: Program yang menggambar-ulang grafik dengan empat kurva fungsi rapat 
#                kementakan normal di atas secara semirip mungkin.
#                Finandi 11/11/2021


# Menampilkan judul program
print('KurvaNormal.py')
print('--------------')

# Memanggil pustaka
import numpy as np
import matplotlib.pyplot as plt
from math import *

# Membuat larik
n = 100 # cacah titik
x = np.linspace(-5,5,n)

# Membuat definisi fungsi
def y(x, miu, s):
    y = 1/(s*sqrt(2*pi))*e**(-1/2*((x-miu)/s)**2)
    return y

# Membuat variable 
miu1 = 0
miu2 = 0
miu3 = 0
miu4 = -2
s1 = sqrt(0.2)
s2 = sqrt(1.0)
s3 = sqrt(5.0)
s4 = sqrt(0.5)
# Memasukkan koordinat
y1 = y(x, miu1, s1)
y2 = y(x, miu2, s2)
y3 = y(x, miu3, s3)
y4 = y(x, miu4, s4)

# Membuat grafik
grafik = plt.figure()
plt.xlabel('$ x $', fontsize = 14)
plt.ylabel(r'$y = \varphi_{\mu, \sigma^2}(x) $', fontsize = 14) # Menyesuaikan ukuran font
plt.plot(x,y1,'b-')                                             # Membuat variasi warna sesuai pada gambar
plt.plot(x,y2,'r-')
plt.plot(x,y3,'y-')
plt.plot(x,y4,'g-')
plt.xticks([i for i in range(-5, 6)])                           # membuat range pada titik-titik di sumbu-x
plt.yticks([i*0.2 for i in range(6)])                           # membuat range pada titik-titik di sumbu-y
plt.legend(['μ = 0,  σ² = 0.2,', 'μ = 0,  σ² = 1.0,', 'μ = 0,  σ² = 5.0,', 'μ = -2, σ² = 0.5,'])
plt.grid()
# Menampilkan grafik
plt.show()

# Menyimpan berkas dalam bentuk file PNG
grafik.savefig('KurvaNormal.png')
```

    
### <span style="color:blue">Tugas #4: Pembandingan Kurva &#8594; 20 poin</span>

Untuk menilai pengaruh dua fungsi matematika yang berbeda dapat dilakukan dengan membandingkan tampilan kurva-kurva dari kedua fungsi tersebut di dalam satu grafik yang sama. Kode-sumber Bahasa Python di bawah ini bertujuan menampilkan suatu kurva parabola:
<p>
<center><img src="parabola.png"></center>
 
<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `BandingkanKurva.py` yang melakukan langkah-langkah berikut:

1. Salin dan jalankan kode-sumber di atas dan pelajari kurva parabola yang tampil.
2. Ubahlah baris `y = x*(2 - x)` menjadi `y1 = x*(2 - x)`.
3. Tambahkan baris kode-sumber baru: `y2 = np.cos(18 * np.pi * x)`.
4. Sesuaikan baris-baris kode-sumber di bawah `import matplotlib.pyplot as plt` sehingga dapat menampilkan dua kurva `x` vs `y1` dan `x` vs `y2` dalam satu grafik yang sama.
5. Jalankan kode-sumber yang sudah disesuaikan dan pelajari kedua kurva yang tampil.

Apakah kurva kedua adalah pendekatan yang tepat terhadap kurva pertama? Apakah anda dapat memperbaiki pendekatan ini?
```
#BandingkanKurva.py: Program yang melakukan langkah-langkah berikut:
#                    1. Salin dan jalankan kode-sumber di atas dan pelajari kurva parabola yang tampil.
#                    2. Ubahlah baris y = x*(2 - x) menjadi y1 = x*(2 - x).
#                    3. Tambahkan baris kode-sumber baru: y2 = np.cos(18 * np.pi * x).
#                    4. Sesuaikan baris-baris kode-sumber di bawah import matplotlib.pyplot as plt sehingga dapat 
#                       menampilkan dua kurva x vs y1 dan x vs y2 dalam satu grafik yang sama.
#                    5. Jalankan kode-sumber yang sudah disesuaikan dan pelajari kedua kurva yang tampil.
#                    Finandi 11/11/2021


# Menampilkan judul program
print('BandingkanKurva.py')
print('------------------')

# Memanggil pustaka
import numpy as np
import matplotlib.pyplot as plt

# Membuat larik
x = np.linspace(0, 2, 20)
y1 = x*(2-x)
y2 = np.cos(18*np.pi*x)

# Memperbaiki pendekatan terhadap kurva pertama
y3 = np.cos((pi*x/2) - (pi/2))

# Membuat grafik
grafik = plt.figure()
plt.plot(x, y1,'b-')
plt.plot(x, y2,'g-')
plt.plot(x, y3,'r-')
plt.legend(['y1 = x*(2-x)', 'y2 = cos(18*pi*x)', 'y3(perbaikan) = cos(pi*x/2 - pi/2)'])
plt.grid()
# Menampilkan grafik
plt.show()

# Membuat kesimpulan
print('Kesimpulan:')
print('-----------')
print('Pendekatan kurva kedua terhadap kurva pertama belum tepat, sehingga diperlukan kurva ketiga (y3) untuk menjawab kasus pendekatan kurva pertama')
```
