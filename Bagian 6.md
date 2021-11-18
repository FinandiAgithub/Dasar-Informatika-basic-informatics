# basic-informatics (Python) #6


### <span style="color:blue">Tugas #1: Baris Perintah dan Pekecualian &#8594; 20 poin</span>

Ketika seorang pengguna menjalankan program melalui Baris Perintah dalam lingkungan Terminal atau <i>Command Prompt</i> mungkin saja ia membuat kesalahan yang tekait dengan pemberian argumen-argumen yang diperlukan agar pogram dapat bekerja secara benar. Beberapa kesalahan yang mungkin terjadi beserta jenis kesalahannya menurut <i>interpreter</i> Python, antara lain:

- tidak memberikan argumen sama sekali sesuai yang diperlukan $\rightarrow$ `IndexError`
- argumen yang diberikan tidak dapat diubah menjadi tipe yang seharusnya $\rightarrow$ `ValueError`
- cacah argumen yang diberikan tidak sebanyak yang diperlukan $\rightarrow$ `IndexError`

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `KonversiFkeC_6.py` yang merupakan perluasan dari progam yang telah dibuat sebelumnya: `KonversiFkeC_2.py` ketika melakukan Kerja Lab PDI-06.

Progam ini menerima suhu dalam satuan Fahrenheit yang diberikan pengguna program melalui Baris Perintah dan menampilkan suhu tersebut dalam satuan Celsius pada layar komputer. Namun, kalau terjadi kesalahan ketika pengguna memberikan masukannya maka program ini dapat menangani kesalahan tesebut dengan menggunakan perkecualian berupa stuktur `try-except`.

<b>Petunjuk</b>: Selidiki dulu jenis kesalahan apa saja yang mungkin tejadi ketika pengguna program memberikan masukannya. Lalu, sediakan penanganan untuk setiap jenis kesalahan di dalam blok perintah setelah kata-kunci `except`.
```
#KonversiFkeC_6.py : Program yang menerima suhu dalam satuan Fahrenheit yang diberikan pengguna program melalui
#                    Baris Perintah dan menampilkan suhu tersebut dalam satuan Celsius pada layar komputer
#                    Finandi 28/10/2021


# Menambah pustaka untuk memanfaatkan baris perintah
import sys

# Menambah argumen, pengecualian, dan menampilkan hasil
try :
    derF = float(sys.argv[1])
    derC = (derF - 32) * (5 / 9)
    print('\nSuhu %g derF = %g derC' % (derF, derC))
except ValueError as obyekExcep :
    if str(obyekExcep) == 'math domain error':
        print('\nSuhu diberikan tidak dapat dikonversi menjadi celcius')
    else : 
        print('\nAnda memberikan input yang bukan bilangan')
except IndexError:
    print('\nMohon berikan angka sesuai kebutuhan program')
except :
    print('\nMohon dicek kembali, Terjadi kesalahan misterius')
```

```
%run KonversiFkeC_6.py 80.6
```

```
# Uji Kesalahan
%run KonversiFkeC_6.py Lapan puluh koma enam
%run KonversiFkeC_6.py 1*779
```

### <span style="color:blue">Tugas #2: Jarak untuk Menghentikan Mobil &#8594; 25 poin</span>

Seorang pengendara sedang menjalankan mobilnya pada laju awal $v_0$ dan lalu secara mendadak mengenakan rem (<i>brake</i>) pada kenderaannya. Berapakah jarak pengereman $d$ yang diperlukan agar dapat menghentikan mobil tersebut? Dengan menerapkan Hukum Gerakan yang kedua dari Newton atau persamaan tenaga yang terkait dapat dijabarkan:

$$ d = \frac{1}{2} \, \frac{v_0^2}{\mu \, g} \quad\quad\quad (1) $$

dengan $\mu$ adalah koefisien gesekan dan $g$ adalah percepatan gravitasi.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `JarakPengereman_1.py` yang menampilkan hasil perhitungan rumus (1) ketika laju awal $v_0$ dan koefisien gesekan $\mu$ diberikan pengguna progam secara interaktif melalui papan-ketik. Jalankan progam tersebut untuk dua kasus dengan laju awal: $v_0 = 120$ km/jam dan $v_0 = 50$ km/jam serta $\mu = 0.3$ (tanpa dimensi) pada kedua kasus tersebut.

```
#JarakPengereman_1.py : Program yang menampilkan hasil perhitungan rumus (1) ketika laju awal v0 
#                       dan koefisien gesekan miu diberikan pengguna progam secara interaktif melalui papan-ketik
#                       Finandi 28/10/2021


# Menampilkan udul Program
print('Jarak untuk Menghentikan Mobil')
print('---------------------------------')

# Melakukan definisi fungsi jarak pengereman dan input rumus
def pengereman(v0,miu):
    g = 9.81                # m/s**2
    d = v0**2 / (2*miu*g)   # Hukum Gerakan kedua Newton (m)
    return d

# Membuat user input kecepatan awal 1 dan 2
v1 = float(input('\nIsikan kecepatan awal mobil (km/jam) : '))
miu1= float(input('Isikan koefisien gesekan(1)  : '))
v2 = float(input('\nIsikan kecepatan awal mobil (km/jam) : '))
miu2= float(input('Isikan koefisien gesekan(2)  : '))

# Mengkonversi satuan km/jam ke m/s
v01 = (1000/3600)*(v1)     
v02 = (1000/3600)*(v2)

# Memanggil fungsi pengereman
d1 = pengereman(v01,miu1)
d2 = pengereman(v02,miu2)

# Menampilkan hasil perhitungan jarak pengereman
print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v1, miu1, d1))
print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v2, miu2, d2))
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `JarakPengereman_2.py` yang menampilkan hasil perhitungan rumus (1) ketika laju awal $v_0$ dan koefisien gesekan $\mu$ diberikan pengguna progam melalui Baris Perintah dalam lingkungan Teminal atau <i>Command Prompt</i>. Jalankan progam tersebut untuk dua kasus dengan laju awal: $v_0 = 120$ km/jam dan $v_0 = 50$ km/jam serta $\mu = 0.3$ (tanpa dimensi) pada kedua kasus tersebut.

```
#JarakPengereman_2.py : Program yang menampilkan hasil perhitungan rumus (1) ketika laju awal  𝑣0  dan koefisien gesekan  𝜇 
#                       diberikan pengguna progam melalui Baris Perintah dalam lingkungan Teminal atau Command Prompt.
#                       Finandi 28/10/2021


# Judul Program
print('Jarak untuk Menghentikan Mobil')
print('---------------------------------')

# Menambahkan pustaka untuk memanfaatkan baris perintah
import sys

# Melakukan definisi fungsi jarak pengereman dan input rumus
def pengereman(v0,miu):
    g = 9.81                # m/s**2
    d = v0**2 / (2*miu*g)   # Hukum Gerakan kedua Newton (m)
    return d

# Membuat user input kecepatan awal 1 dan 2
v1 = float(sys.argv[1])
miu1= float(sys.argv[2])
v2 = float(sys.argv[3])
miu2= float(sys.argv[4])

# Konversi satuan km/jam ke m/s
v01 = (1000/3600)*(v1)     
v02 = (1000/3600)*(v2)

# Memanggil fungsi pengereman
d1 = pengereman(v01,miu1)
d2 = pengereman(v02,miu2)

# Menampilkan hasil perhitungan jarak pengereman
print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v1, miu1, d1))
print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v2, miu2, d2))
```

```
%run JarakPengereman_2.py 120 0.3 50 0.3
```

```
# Menguji kesalahan program
%run JarakPengereman_2.py 0 0 0 0
```

Kesalahan yang didapat adalah = ZeroDivisionError: float division by zero

### <span style="color:blue">Tugas #3: Perluasan dengan Perkecualian &#8594; 20 poin</span>

Sudah menjadi praktik pemrograman yang lazim dilakukan: setelah suatu program dengan masukan pengguna dapat berjalan baik maka selanjutnya sang pemrogam berusaha mencari berbagai cara untuk menimbulkan kesalahan dan kemudian cara mengatasinya.

Ketika seorang pengguna memberi masukan baik secara interaktif dengan papan-ketik maupun melalui Baris Perintah, mungkin saja ia membuat kesalahan sehingga <i>interpeter</i> Python memunculkan pesan kesalahan yang mengandung info tentang jenis kesalahan seperti: `IndexError`, `NameError`, `TypeError`, `ValueError`, `ZeroDivisionError`, dan sebagainya.

Untuk menangani kesalahan yang muncul, Bahasa Python menyediakan stuktur perkecualian (<i>exception</i>) yang berbentuk stuktur `try-except`.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `JarakPengereman_3.py` yang merupakan perluasan terhadap program `JarakPengereman_1.py` yang telah dibuat sebelumnya. Pada perluasan ini, selidiki dulu jenis kesalahan apa saja yang mungkin tejadi ketika pengguna program memberikan masukannya melalui papan-ketik. Lalu, sediakan penanganan untuk setiap jenis kesalahan di dalam blok perintah setelah kata-kunci `except`.

```
#JarakPengereman_3.py : Program yang merupakan perluasan terhadap program 
#                       JarakPengereman_1.py yang telah dibuat sebelumnya
#                       Finandi 28/10/2021


# Judul Program
print('Perluasan dengan Perkecualian')
print('---------------------------------')

# Melakukan definisi fungsi jarak pengereman dan input rumus
def pengereman(v0,miu):
    g = 9.81                # m/s**2
    d = v0**2 / (2*miu*g)   # Hukum Gerakan kedua Newton (m)
    return d

# Menambahkan argumen, perkecualian dan menampilkan hasil perhitungan
# kode sama seperti JarakPengereman_1.py
try:
    v1 = float(input('Masukan kecepatan awal mobil (km/jam) : '))
    miu1= float(input('Masukan koefisien gesekan(1)  : '))
    v2 = float(input('Masukan kecepatan awal mobil (km/jam) : '))
    miu2= float(input('Masukan koefisien gesekan(2)  : '))
    v01 = (1000/3600)*(v1)
    v02 = (1000/3600)*(v2)
    d1 = pengereman(v01,miu1)
    d2 = pengereman(v02,miu2)
    print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v1, miu1, d1))
    print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v2, miu2, d2))

# Pengecualian
except ValueError as kk :
    if str(kk) == 'math domain error' :
        print('\nMohon masukkan angka dengan benar')
    else :
        print('\nInput yang anda berikan bukan bilangan')
except ZeroDivisionError :   # Hasil error seperti padapercobaan JarakPengereman_2.py
    print('\nAnda memberikan input yang mengakibatkan pembagian nol')
except :
    print('\nMohon dicek kembali, Terjadi kesalahan misterius')
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `JarakPengereman_4.py` yang merupakan perluasan terhadap program `JarakPengereman_2.py` yang telah dibuat sebelumnya. Pada perluasan ini, selidiki dulu jenis kesalahan apa saja yang mungkin tejadi ketika pengguna program memberikan masukannya melalui Baris Perintah. Lalu, sediakan penanganan untuk setiap jenis kesalahan di dalam blok perintah setelah kata-kunci `except`.

```
#JarakPengereman_4.py : Program yang yang merupakan perluasan terhadap program JarakPengereman_2.py
#                       yang telah dibuat sebelumnya.
#                       Finandi 28/10/2021


# Judul Program
print('Perluasan dengan Perkecualian')
print('---------------------------------')

# Memasukkan modul/pustaka
import sys

# Melakukan definisi fungsi jarak pengereman dan input rumus
def pengereman(v0,miu):
    g = 9.81                # m/s**2
    d = v0**2 / (2*miu*g)  # Hukum Gerakan kedua Newton (m)
    return d

# Menambahkan argumen, perkecualian dan menampilkan hasil perhitungan
try:
    v1 = float(sys.argv[1])
    miu1= float(sys.argv[2])
    v2 = float(sys.argv[3])
    miu2= float(sys.argv[4])
    v01 = (1000/3600)*(v1)
    v02 = (1000/3600)*(v2)
    d1 = pengereman(v01,miu1)
    d2 = pengereman(v02,miu2)
    print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v1, miu1, d1))
    print('\nJika kecepatan awal mobil adalah %g km/jam dan koefisien gesek %g maka' \
       ' jarak pengereman sampai berhenti adalah %g meter' % (v2, miu2, d2))

# Pengecualian
except ValueError as kk :
    if str(kk) == 'math domain error' :
        print('\nMohon masukkan angka dengan benar')
    else :
        print('\nInput yang anda berikan bukan bilangan')
except ZeroDivisionError :   # Hasil error seperti padapercobaan JarakPengereman_2.py
    print('\nAnda memberikan input yang mengakibatkan pembagian nol')
except :
    print('\nMohon dicek kembali, Terjadi kesalahan misterius')
```

```
# Menguji sesuai data 
%run JarakPengereman_4.py 120 0.3 50 0.3 
print()

# Menguji kesalahan
%run JarakPengereman_4.py 0 0 a 0 
```
