# basic-informatics
A list of basic informatics skills (Python)


### <span style="color:blue">Tugas #1: <i>Debugging</i> &#8594; 30 poin</span>
Penentuan sumber kesalahan dan perbaikannya (<i>debugging</i>) merupakan suatu keahlian yang penting dalam pemrograman komputer. Ada dua golongan kesalahan pada suatu program, yakni
- <b>Kesalahan sintaksis</b> atau kesalahan penulisan yang membuat program tidak berjalan hingga tuntas dan <i>interpreter</i> atau <i>compiler</i> menampilkan pesan kesalahan serta kemungkinan letak sumber kesalahan. Pemrogram harus mampu menafsirkan arti dari pesan tersebut, memastikan letak sumber kesalahan dan memperbaiki kesalahan yang dimaksud.
- <b>Kesalahan logika</b> yang tidak menimbulkan pesan kesalahan namun program menghasilkan output yang salah atau bukan seperti yang diinginkan. Berbekalkan algoritma yang mendasari program, pemrogram harus menelusuri lagi baris-per-baris kode-sumber untuk menentukan letak sumber kesalahan ini dan memperbaikinya.

Seorang pemrogram telah menulis kode-sumber seperti di bawah ini:
```
C = A + B
A = 3
B = 2
print(C)
```
<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah semua sumber kesalahan dari program empat baris di atas dan kemudian perbaikilah sehingga program tersebut dapat berjalan dengan benar.
```
#kode yang salah
#    C = A + B ----------> 1. C merupakan variabel dari operasi variabel A & B,
#                             sehingga seharusnya variabel A & B berada sebelum C
#    A = 3
#    B = 2
#    print(C)


#perbaikan kesalahan
A = 3
B = 2
C = A + B
print(C)
```


Pemrogram yang lain hendak menulis kode-sumber yang dapat menghitung nilai <i>tangent</i> dari dua sudut yang berbeda:
```
from math import pi, tan
tan = tan(pi / 4)
tan2 = tan(pi / 3)
print(tan, tan2)
```
<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah semua sumber kesalahan dari program lima baris di atas dan kemudian perbaikilah sehingga program tersebut dapat berjalan dengan benar. Ujilah kebenaran hasil kerja program anda dengan menggunakan kalkulator ilmiah.
```
#kode yang salah
#    from math import pi, tan
#    tan = tan(pi / 4) ----------> 1. fungsi tan berubah menjadi variabel
#    tan2 = tan(pi / 3)
#    print(tan, tan2)

print('Perbandingan dengan hasil kalkulator\n')

#perbaikan kesalahan
from math import pi, tan
tan1 = tan(pi / 4)
tan2 = tan(pi / 3)
print('hasil program')
print(tan1, 'dan', tan2,'\n')

#hasil kalkulator ilmiah
tan1x = 1
tan2x = 1.73205
print('hasil kalkulator')
print(tan1x,'dan', tan2x)
```


### <span style="color:blue">Tugas #2: Massa dari Berbagai Bahan &#8594; 20 poin</span>
Massa dari berbagai bahan dapat ditentukan berdasarkan rapat massanya. Rapat massa $\rho$ dari suatu bahan didefinisikan dengan rumus:
$$ \rho = \frac{m}{V}  $$
dengan $m$ adalah massa bahan tersebut yang terdapat di dalam suatu volume sebesar $V$.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python __lengkap__ bernama `MassaBahan.py` yang menghitung dan menampilkan secara rapi massa (gram) dalam satu liter dari bahan-bahan berikut: besi, udara, minyak, es, tubuh manusia, perak dan platinum.
<b>Petunjuk</b>: Gunakan data rapat massa (g/cm$^3$) dari berbagai bahan yang tersimpan di dalam berkas bernama `rapat_massa.dta` yang terdapat di dalam direktori/<i>folder</i> yang sama dengan berkas `LapPDI-02-888888.ipynb` ini. Berkas `rapat_massa.dta` berformat teks sehingga dapat dibaca dengan memakai <i>Jupyter Notebook</i>.
```
# MassaBahan.py: Program Python untuk menghitung dan menampilkan secara
#                rapih massa (gram) dalam satu liter dari bahan.

# Tampilkan judul program
print("Menghitung & Menampilkan massa dari suatu bahan")
print("-------------------------------------------------\n")

# Menetapkan variabel menggunakan data yang telah diketahui dari berkas rapat_massa.dta
listBahan = ["Besi", "Udara", "Minyak", "Es", "Tubuh Manusia", "Perak", "Platinum"] # Nama Bahan
listRho   = [7.8, 0.0012, 0.67, 0.9, 1.03, 10.5, 21.4]                              # Rapat massa dari bahan (g/cm^3)
volume    = 1000                                                                    # Volume dalam cm^3

# Membuat list kosong untuk menampung nilai massa
listMassa = []

# Menghitung Massa dengan menggunakan perulangan
for i in range(len(listBahan)):
    H    = listRho[i] * volume                                                      # Menghitung nilai massa pada setiap bahan
    listMassa.append(H)                                                             # Memasukan nilai massa ke dalam list
    
# Menampilkan tabel bahan, rapat massa, dan massa menggunakan perulangan.
print('----------------------------------------------------')
print('|Bahan         |Rapat Massa (g/cm^3) |massa (gram) |')
print('----------------------------------------------------')
for i in range(len(listBahan)):
    Bahan = listBahan[i]
    Rho   = listRho[i]
    Massa = listMassa[i]
    print('|%-13s |%20s |%12.1f |' % (Bahan, str(Rho), Massa))
print('----------------------------------------------------')
```


### <span style="color:blue">Tugas #3: Gaya Hambat &#8594; 20 poin</span>
Gaya hambat atau <i>drag force</i>, yang diakibatkan adanya halangan udara, pada suatu benda dapat diyatakan sebagai rumus berikut:
$$ F_d = \frac{1}{2} \, C_d \, \rho \, A \, v^2 $$
dengan
- $C_d$ = koefisien hambat (<i>drag coefficient</i>) yang nilainya sangat tergantung
pada bentuk benda dan kekasaran permukaan benda;
- $\rho$ = kerapatan udara = 1,2 kg/m$^3$;
- $A$ = luas penampang (tegak lurus terhadap arah gerakan) benda; dan
- $v$ = kecepatan benda.
Rumus di atas dapat dipakai untuk menghitung gaya hambat yang dialami suatu bola kaki ketika ditendang.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `GayaHambat.py` yang menghitung gaya hambat saat suatu bola ditendang. Untuk suatu bola kaki berjejari 11 cm dengan massa = 0,43 kg, koefisien hambat yang terkait adalah 0,4. Tampilkan gaya hambat pada bola tersebut ketika ditendang keras ($v$ = 120 km/jam) dan ketika ditendang lunak ($v$ = 30 km/jam).
```
# GayaHambat.py: Program Python untuk menghitung gaya hambat saat suatu bola ditendang

# Gaya Hambat Pada Bola
print("Gaya Hambat Pada Bola\n")

# memanggil modul 
from math import *

#tetapan nilai variabel
Cd = 0.4                                                      # Koefisien hambat
p  = 1.2                                                      # Kerapatan udara (kg/m^3)
m  = 0.43                                                     # Massa (kg)
r  = 11                                                       # Jari-jari (cm)
v  = {"keras": 120, "lunak": 30}                              # Kecepatan saat ditendang keras/lunak (km/jam)

# Mengubah satuan variabel
rm  = r / 100                                                 # Jari-jari (m)
v["keras"] = round(v["keras"] * 0.277778, 3)                  # Kecepatan saat ditendang keras (m/s)
v["lunak"] = round(v["lunak"] * 0.277778, 3)                  # Kecepatan saat ditendang lunak (m/s)

# Menghitung luas permukaan bola
A  = 4*pi*(rm**2)

# Menghitung, menyimpan, dan menampilkan gaya hambat
GayaHambat = {}                                               # Dictionary kosong untuk menyimpan
for key in v :
    Fd = (1/2)*Cd*p*A*(v[key]**2)                             # Rumus gaya hambat
    GayaHambat.update({key: Fd})                              # Menyimpan gaya hambat untuk digunakan pada tugas 4
    print("Gaya hambat saat bola ditendang {} adalah {} N" \
          .format(key, round(Fd, 3)))
```


### <span style="color:blue">Tugas #4: <i>String</i> Gaya Gravitasi &#8594; 20 poin</span>
Gaya gravitasi pada suatu benda dapat dinyatakan dengan rumus:
$$ F_g = m \, g $$
dengan
- $m$ = massa benda; dan
- $g$ = percepatan gravitasi = 9,81 m/s$^2$.
Mirip <font style="color:blue">Tugas #3</font>, rumus di atas dapat dipakai untuk menghitung gaya gravitasi yang dialami suatu bola kaki ketika ditendang.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `GayaGravitasi.py` yang menghitung gaya gravitasi yang dialami suatu bola saat ditendang. Bola yang ditinjau adalah bola yang sama pada <font style="color:blue">Tugas #3</font>. Selain itu, program ini juga menghitung rasio antara gaya hambat dan gaya gravitasi pada bola tersebut ketika ditendang keras ($v$ = 120 km/jam) dan ketika ditendang lunak ($v$ = 30 km/jam).
```
# GayaGravitasi.py: Program Python untuk menghitung gaya gravitasi
#                   yang dialami suatu bola saat ditendang.

# Tampilkan judul
print("Menghitung gaya gravitasi bola")
print("-------------------------")

# Menetapkan variabel
g = 9.81                                                                                    # Percepatan gravitasi (m/s^2)
m = 0.43                                                                                    # Massa (kg)

# Menghitung gaya gravitasi
Fg = m * g


# Menampilkan gaya gravitasi
print("Gaya gravitasi yang dialami bola sebesaar {} N \n"\
      .format(round(Fg, 3)))

# Menampilkan judul
print("\nMenghitung rasio antara gaya hambat dan gaya gravitasi")
print("------------------------------------------------------")

# Menampilkan gaya hambat yang telah dikalkulasi pada tugas 3
for key in GayaHambat :
    print("Gaya hambat saat bola ditendang {} ialah {} N"\
          .format(key, round(GayaHambat[key], 3)))
    
# Menghitung dan menampilkan rasio antara gaya hambat dan gaya gravitasi
print()
for key in GayaHambat :
    rasio = GayaHambat[key] / Fg
    print("Rasio antara gaya hambat bola ditendang {} dan gaya gravitasi bola adalah {}"\
          .format(key, round(rasio, 3)))
```
