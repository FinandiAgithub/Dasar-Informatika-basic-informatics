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



