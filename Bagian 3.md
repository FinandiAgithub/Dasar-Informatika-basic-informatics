# basic-informatics (Python) Part #3


### <span style="color:blue">Tugas #1: Koordinat Titik Berjarak Seragam &#8594; 20 poin</span>
Ketika bekerja dengan titik-titik pada bidang datar dengan sumbu koordinat, terkadang dibutuhkan sekumpulan titik dengan jarak yang seragam di antara mereka. Koordinat-$x$ dari $n + 1$ titik seperti itu dapat dibangkitkan di dalam rentang $[a, b]$ dengan algoritma sebegai berikut:
1. Mulai dengan suatu <i>list</i> kosong
2. Hitung jarak seragam $h$ yang memisahkan $n + 1$ titik di dalam rentang $[a, b]$ dengan rumus:
$$ h = \frac{b - a}{n} $$
3. Gunakan kalang `for` untuk membangkitkan setiap koordinat-$x$ dari titik-titik yang dimaksud dan imbuhkan setiap titik ke dalam <i>list</i> yang sudah disiapkan
4. Tampilkan <i>list</i> yang dihasilkan

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python __lengkap__ bernama `KoordinatTitik.py` yang menghitung dan menampilkan koordinat-$x$ dari $n + 1$ titik yang berjarak seragam di dalam rentang $[a, b]$ seperti pada algoritma di atas. Tetapkan cacah titik `n` serta batas-batas rentang: `a` dan `b` pada bagian awal program anda.
```
# KoordinatTitik.py: menghitung dan menampilkan koordinat- 𝑥  dari  𝑛+1  
#                    titik yang berjarak seragam di dalam rentang  [𝑎,𝑏]
#                    Finandi 22/09/2021

# Tampilkan judul program
print('Menghitung dan menampilkan koordinat-𝑥 dari 𝑛+1 titik')
print('-----------------------------------------------------\n')

# Penentuan variabel
koordinat_x = []
n = 15              # banyak selang antara titik koordinat
a = 0               # batas awal 
b = 15              # batas akhir
h = (b-a)/n         # jarak seragam ℎ yang memisahkan 𝑛+1 titik di dalam rentang [𝑎,𝑏]  

# Kalang for untuk membangkitkan setiap koordinat- 𝑥 dari titik-titik 
for i in range (0, n+1):
    X = a + i*h
    koordinat_x.append(int(X))
# Menampilan hasil
print ('jarak seragam ℎ yang memisahkan 𝑛+1 titik di dalam rentang [𝑎,𝑏] adalah %0.1f' % (h))
print('\nkoordinat-𝑥 dari 𝑛+1 titik yang berjarak seragam di dalam rentang [0,10] :')
print(koordinat_x)
```


### <span style="color:blue">Tugas #2: Tabel Posisi Bola &#8594; 30 poin</span>
Suatu bola yang dilambungkan pada arah tegak akan menempuh posisi koordinat-$y$ yang mula-mula semakin bertambah tinggi namun berikutnya semakin berkurang merendah hingga mencapai posisi awalnya. Posisi bola tersebut pada setiap saat $y(t)$ ditentukan oleh laju awal ketika dilambungkan $v_0$ dan pecepatan gravitasi $g$ seperti pada rumus berikut:
$$ y(t) = v_0 \, t - \frac{1}{2} \, g \, t^2  $$
dengan $g = 9.8$ m/s$^2$. Bola tersebut akan kembali mencapai posisi awalnya pada suatu saat $t_1$ yang dapat dihitung dengan rumus di atas dengan menyulihkan $y(t_1) = 0$ sehingga
$$ y(t_1) = v_0 \, t_1 - \frac{1}{2} \, g \, t_1^2 \,\, \rightarrow \,\, 0 = t_1 \left( v_0 - \frac{1}{2} \, g \, t_1 \right) $$
$$ 0 = v_0 - \frac{1}{2} \, g \, t_1 \,\, \Rightarrow \,\, t_1 = \frac{2 \, v_0}{g} $$
Dengan demikian, rentang waktu yang menjadi perhatian ketika bola mulai dilambungkan sampai ia kembali mencapai posisi awalnya adalah $[0, 2 \, v_0 / g]$ sekon.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python __lengkap__ bernama `TabelPosisi_1.py` yang menghitung dan menampilkan tabel secara rapi dari posisi tegak bola sejak dilambungkan dengan laju awal $v_0 = 12$ m/s hingga kembali mencapai posisi awalnya. 
<b>Petunjuk</b>: Gunakan kalang `while` untuk menentukan posisi bola pada `n + 1` nilai waktu $t$ yang berjarak seragam di dalam rentang waktu $[0, 2 \, v_0 / g]$ sekon.
```
# TabelPosisi_1.py : menghitung dan menampilkan tabel secara rapi dari posisi tegak bola sejak
#                    dilambungkan dengan laju awal 𝑣0=12 m/s hingga kembali mencapai posisi awalnya.
#                    Finandi 22/09/2021


# Rentang waktu berada pada [0,2 v0/g]
v0  = 12                  # m/s    
g   = 9.8                 # m/s^2
ti  = 0                   # batas awal waktu (sekon)  
tf  = (2 * v0) / g        # batas akhir waktu (sekon)
n   = 5                   # banyak lompatan waktu yang seragam
dt  = (tf - ti) / n       # lompatan waktu


# Kalang while untuk menentukan posisi bola pada n + 1 nilai waktu 𝑡 
# yang berjarak seragam di dalam rentang waktu [0,2v0/g] sekon.
print ('Tampilan waktu dan posisi bola')
print ('------------------------------\n')
print('\n  Waktu (s)    Jarak (m) ')
print('-------------------------')
t = 0
while t <= tf :
     y = v0*t - 1/2*(g*t**2)
     print ('|%f s | %f m|' %(t,y))
     t += dt
print('-------------------------')
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python __lengkap__ bernama `TabelPosisi_2.py` yang menghitung dan menampilkan tabel secara rapi dari posisi tegak bola sejak dilambungkan dengan laju awal $v_0 = 12$ m/s hingga kembali mencapai posisi awalnya. 
<b>Petunjuk</b>: Gunakan kalang `for` untuk membuat dua <i>lists</i> yang diperlukan:
- <i>list</i> yang berisikan `n + 1` nilai waktu $t$ yang berjarak seragam di dalam rentang waktu $[0, 2 \, v_0 / g]$ sekon; dan
- <i>list</i> yang berisikan nilai-nilai $y(t)$ pada saat $t$ terkait.
Gunakan kalang `for` yang terakhir untuk menampilkan isi kedua <i>lists</i> tersebut dalam bentuk tabel yang rapi.
```
# TabelPosisi_2.py : menghitung dan menampilkan tabel secara rapi dari posisi tegak bola sejak
#                    dilambungkan dengan laju awal 𝑣0=12 m/s hingga kembali mencapai posisi awalnya.
#                    Finandi 22/09/2021


# Rentang waktu berada pada [0,2 v0/g]
v0  = 12                  # m/s    
g   = 9.8                 # m/s^2
ti  = 0                   # batas awal waktu (sekon)  
tf  = (2 * v0) / g        # batas akhir waktu (sekon)
n   = 5                   # banyak lompatan waktu yang seragam
dt  = (tf - ti) / n       # lompatan waktu


# Kalang while untuk menentukan posisi bola pada n + 1 nilai waktu 𝑡 
# yang berjarak seragam di dalam rentang waktu [0,2v0/g] sekon.
print ('Tampilan waktu dan posisi bola')
print ('------------------------------\n')
print('\n  Waktu (s)    Jarak (m) ')
print('-------------------------')
t=0
for i in range(0, n+1) :
     y = v0 * t - (1/2 * (g * t**2 ))
     print ('|%f s | %f m|' %(t,y))
     t += dt
print('-------------------------')
```


### <span style="color:blue">Tugas #3: Tenaga Atom Hidrogen &#8594; 25 poin</span>
Tenaga yang dilepaskan oleh elektron atom Hidrogen ketika melakukan peralihan dari aras (<i>level</i>) tenaga $n_i$ menuju aras $n_f$ ditentukan dengan rumus berikut:
$$ \Delta{E} = -\frac{m_e \, e^4}{8 \, \epsilon_0^2 \, h^2} \cdot \left( \frac{1}{n_i^2} - \frac{1}{n_f^2} \right) $$
dengan
- $m_e = 9.1094 \times 10^{-31}$ kg : massa elektron
- $e = 1.6022 \times 10^{-19}$ C : muatan elementer
- $\epsilon_0 = 8.8542 \times 10^{-12}$ C$^2$s$^2$kg$^{-1}$ : pemitivitas listrik dari ruang vakum
- $h = 6.6261 \times 10^{-34}$ Js : tetapan Planck

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `AlihTenagaHidogen.py` yang menghitung tenaga yang dilepaskan elektron dari atom Hidrogen ketika beralih dari aras $n_i$ ke aras $n_f$ dengan $n_i, n_f = 1, 2, \dots, 5$. Perhitungan semua tenaga peralihan tersebut dilakukan dengan menggunakan kalang `for`.
<b>Petunjuk</b>: Tampilkan hasil perhitungan di dalam tabel yang rapi dengan 3 kolom, yakni $n_i, n_f$ dan $\Delta{E}$. Perhatian satuan tenaga yang dipergunakan dalam perhitungan program ini.
```
# AlihTenagaHidogen.py: Program Python untuk menghitung tenaga yang 
#                       dilepaskan elektron dari atom Hidrogen.
#                       Finandi 22/09/2021


# Tampilkan judul program
print("Tenaga Dilepas Atom Hidrogen")
print("----------------------------\n")

# Pemberian variabel
me = 9.1094 * (10**(-31))
e  = 1.6022 * (10**(-19))
e0 = 8.8542 * (10**(-12))
h  = 6.6261 * (10**(-34))
ni = [1, 2, 3, 4, 5]
nf = [1, 2, 3, 4, 5]

# Pembuatan header list
print("|   ni  |   nf  |    Δ𝐸    |")
print("----------------------------")
# Pembuatan kalang for 
for i in ni:
    for j in nf:
        E = (-(me*(e**4))/(8*(e0**2)*(h**2))) * ((1/(i**2)) - (1/(j**2)))
        print("| %4.0d  | %4.0d  |%10.2E|" %(i, j, E))
print("----------------------------")
```


### <span style="color:blue">Tugas #4: Jumlah Deret &#8594; 15 poin</span>
Kode-sumber di bawah ini dimaksudkan untuk menghitung jumlah:
$$ s = \sum_{k = 1}^M \frac{1}{k} $$
namun kode-sumber berikut masih mengandung beberapa kesalahan:
```
s = 0;  k = 1;  M = 100
while k < M:
    s += 1 // k
print(s)
```
Ada dua cara untuk memperbaiki kesalahan dalam suatu program, yakni:
- Baca secara cermat seluruh baris kode-sumber dari program yang sedang diperiksa dan bayangkan akibat dari setiap baris kode-sumber.
- Tampilkan setiap keluaran sementara dari kode-sumber terkait dan bandingkan dengan hasil perhitungan yang dilakukan secara manual.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah semua sumber kesalahan dari program empat baris di atas dan kemudian perbaikilah sehingga program tersebut dapat berjalan dengan benar. Ujilah kebenaran hasil kerja program anda dengan menggunakan kalkulator ilmiah.
<b>Petunjuk</b>: Kalau terjadi perulangan-tanpa-batas (<i>infinite loop</i>) ketika memeriksa program empat bais di atas maka gunakan menu `Jupyter Notebook` berikut untuk menghentikannya secara aman: `Kernel | Interrupt`.
```
# Debugging 
# Finandi 22/09/2021

# Program yang salah
# s = 0;  k = 1;  M = 100
# while k < M: ----------------------------> nilai hanya akan sampai 99
#     s += 1 // k -------------------------> penggunaan // akan menghasilkan integer sehingga program akan
#                                            membacanya 1+0+0+0+...+0(ke-100) dan s=1
#      ------------------------------------> tidak adanya k += 1 akan menyebabkan k selalu bernilai 1 sesuai
#                                            seperti variabel awal k = 1, sehingga k tidak akan memenuhi 
#                                            syarat berhenti yang bernilai >= M
# print(s)


# Perbaikan program
s = 0;  k = 1;  M = 100
while k <= M:
    s += 1 / k
    k += 1
print('hasil program', s)

# Uji kebenaran
print("\nhasil dengan kalkulator ilmiah adalah 5.18737")
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulis-ulang program di atas dengan menggunakan kalang `for`.
```
# Perhitungan mengunakan kalang for
# Finandi 22/09/2021


# Penempatan variabel
n = 100               
x = 0
# Penggunaan kalang for
for i in range(1, n+1):
    x += 1/i
print('hasil program', x)

# Uji kebenaran
print("\nhasil dengan kalkulator ilmiah adalah 5.18737")
```
