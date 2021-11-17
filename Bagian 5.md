# basic-informatics (Python) #5


### <span style="color:blue">Tugas #1: Nilai dan Marka &#8594; 20 poin</span>
Seorang guru atau dosen dapat memberi nilai (bilangan) dan marka (huruf) terhadap suatu kuis atau ujian berdasarkan rentang yang baku yang sudah ditetapkan, baik sesuai kesepakatan dengan pendidik lainnya maupun berdasarkan pendapat pribadinya. Rentang yang acap dipergunakan dapat berupa nilai-nilai di antara 0 hingga 10 atau di antara 0 hingga 100; namun tidak menutup kemungkinan sang guru atau dosen menggunakan suatu rentang nilai yang ditentukannya secara pribadi. Aturan pengubahan (konversi) dari nilai menjadi marka juga dapat dilakukan berdasarkan standar tertentu, sesuai kelaziman dalam suatu instansi atau berdasarkan pertimbangan pribadi.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `KonversiNilai_1.py` yang dapat membantu seorang guru/dosen untuk melakukan konversi nilai menjadi marka dari suatu kuis dengan aturan:
Nilai | Marka
:-: | :-:
5 | A
4 | B
3 | C
2 | D
1 | E
0 | K

Ketika program ini dijalankan, pengguna guru/dosen cukup memasukkan nilai (bilangan) seperti pada kolom kiri tabel di atas dan progam menampilkan marka (huruf) yang sesuai seperti pada kolom kanan tabel di atas.
<u>Petunjuk</u>: Gunakan struktur pengambilan keputusan (dengan kata-kunci `if`) untuk menentukan marka dari nilai tertentu yang diberikan melalui papan-ketik (<i>keyboard</i>).
```
# KonversiNilai_1.py: Membantu seorang guru/dosen untuk melakukan konversi nilai menjadi marka dari suatu kuis
#                     Finandi 18/10/2021

# Judul Program
print('Konversi Nilai #1')
print('-----------------')

# Input variable
n = int(input('Nilai(1-5) = '))

# Menjalankan program dengan kondisi
if n == 5 :
    print(n, '= A')
elif n ==4 :
    print(n, '= B')
elif n ==3 :
    print(n, '= C')
elif n ==2 :
    print(n, '= D')
elif n ==1 :
    print(n, '= E')
elif n == 0:
    print(n, '= K')
else:
    print(n, '= tidak terdapat marka')
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislahlah program Python <b>lengkap</b> bernama `KonversiNilai_2.py` yang dapat membantu seorang guru/dosen untuk melakukan konversi rentang nilai menjadi marka dari suatu ujian dengan aturan:

Rentang | Marka
:-: | :-:
90 - 100 | A
80 - 89 | A/B
70 - 79 | B
60 - 69 | B/C
50 - 59 | C
40 - 49 | C/D
30 - 39 | D
0 - 29  | E

Ketika program ini dijalankan, dengan menggunakan papan-ketik pengguna guru/dosen cukup memasukkan suatu nilai (bilangan) dalam salah satu rentang seperti pada kolom kiri tabel di atas dan program menampilkan marka yang sesuai seperti pada kolom kanan tabel di atas.
```
# KoversiNilai_2.py: Membantu seorang guru/dosen untuk melakukan konversi
#                    rentang nilai menjadi marka dari suatu ujian.
#                    Finandi 18/10/2021


# Judul Program
print('Konversi Nilai #2')
print('-----------------')

# Input variable
n = int(float(input('Nilai(0-100) = ')))

# Menjalankan program dengan kondisi
if 90 <= n <= 100 :
    print(n, '= A')
elif 80 <= n <= 89 :
    print(n, '= A/B')
elif 70 <= n <= 79 :
    print(n, '= B')
elif 60 <= n <= 69 :
    print(n, '= B/C')
elif 50 <= n <= 59 :
    print(n, '= C')
elif 40 <= n <= 49 :
    print(n, '= C/D')
elif 30 <= n <= 39 :
    print(n, '= D')
elif 0 <= n <= 29 :
    print(n, '= E')
else:
    print(n, '= tidak terdapat marka')
```


### <span style="color:blue">Tugas #2: Nomor Hari &#8594; 25 poin</span>
Hari-hari dalam setahun seringkali diberi nomor dari 1 hingga 365 (ketika tahun yang biasa) atau 366 (ketika tahun kabisat). Penentuan nomor suatu hari tergantung pada nilai-nilai $bulan$ dan $tanggal$ dari hari yang dimaksud serta harus disesuaikan terhadap bulan yang setelah Februari dan tahun kabisat. Metode yang dipergunakan untuk menentukan $\text{nomorHari}$ terdiri dari 3 langkah di bawah ini yang semuanya menggunakan operasi-operasi bilangan bulat saja:

1.Gunakan rumus berikut:
    $$ \text{nomorHari} = 31 \times (bulan - 1) + tanggal $$
<p>
2.Jika bulan dari hari tersebut adalah setelah Februari maka sesuaikan $\text{nomorHari}$ (yang diperoleh pada langkah 1) dengan mengurangkan
    $$ (4 \times bulan + 23) \, / \, 10 $$
<p>
4.Jika tahun dari hari tersebut adalah tahun kabisat dan hari tersebut ternyata adalah setelah 29 Februari maka sesuaikan $\text{nomorHari}$ (yang diperoleh pada langkah 2) dengan menambahkan $1$.
<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `nomorHari.py` yang menampilkan nomor hari dari suatu hari yang diberikan pengguna program melalui papan-ketik. Pada awal pelaksanaan program, pengguna diminta untuk memberikan tanggal, bulan dan tahun dari hari yang ingin ditentukan nomornya.
<u>Petunjuk</u>: Untuk menentukan apakah tahun dari hari yang ingin ditentukan nomornya adalah termasuk tahun kabisat maka manfaatkan program bernama `TahunKabisat.py` yang telah anda buat pada <b>Kerja #1</b> dalam berkas `LabPDI-05-888888.ipynb`

```
# nomorHari.py: Menampilkan nomor hari dari suatu hari yang 
#               diberikan pengguna program melalui papan-ketik.
#               Finandi 18/10/2021

# Judul Program
print('Nomor Hari')
print('----------')

# Memasukkan variable & mendefinisikan fungsi 
def TahunKabisat():
    # Input variable
    day = int(input('Tanggal = '))
    month = int(input('Bulan = '))
    year = int(input('Tahun = '))
    
    # Menjalankan kondisi terhadap tahun kabisat
    if year % 4 == 0 :
        if year % 100 == 0 and year % 400 != 0:
            year = ('Bukan tahun kabisat')
        else:
            year = ('Tahun kabisat')
    else:
        year = ('Bukan tahun kabisat')
        
    # Perhitungan
    if year == 'Bukan tahun kabisat':
        if month == 1 or month == 2:
            n_day = 31 * (month-1) + day
        else:
            n_day = (31 * (month-1) + day) - ((4 * month + 23) // 10)
    elif year == 'Tahun kabisat':
        if month == 1 or month == 2:
            n_day = 31 * (month - 1) + day
        else:
            n_day = (31 * (month - 1)) - ((4 * month + 23) // 10) + 1
            
    # Menampilkan hasil keluaran
    print ('Nomor hari =',n_day)
        
# Memanggil kembali fungsi
TahunKabisat()
```


### <span style="color:blue">Tugas #3: Pendekatan Terhadap $\pi$ &#8594; 30 poin</span>

Untuk melakukan pendekatan terhadap $\pi$ diperlukan suatu fungsi untuk menghitung panjang dari suatu lintasan (<i>path</i>). Jika suatu benda bergerak mengikuti lintasan tertentu pada bidang datar maka pada $n + 1$ saat (titik waktu) dapat direkam koordinat posisi $(x, y)$ yang terkait pergerakan benda tersebut, yaitu:

$$ (x_0, y_0), \, (x_1, y_1), \, (x_2, y_2), \, \cdots, \, (x_n, y_n) $$.

Panjang keseluruhan lintasan $L$ dari posisi awal $(x_0, y_0)$ hingga posisi akhir $(x_n, y_n)$ adalah jumlah dari semua panjang garis potongan-potongan lintasan: $(x_{i - 1}, y_{i - 1})$ hingga $(x_i, y_i)$ untuk $i = 1, 2, \cdots, n$, yaitu:

$$ L = \sum_{i = 1}^n \sqrt{(x_i - x_{i - 1})^2 + (y_i - y_{i - 1})^2} \quad\quad\quad (1) $$

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah definisi fungsi `panjLintasan(x, y)` yang menghitung panjang keseluruhan lintasan $L$ seusai rumus $(1)$. Argumen-argumen $x$ dan $y$ masing-masing berupa <i>lists</i> yang berisikan nilai-nilai koordinat $x_0, x_1, x_2, \cdots, x_n$ dan $y_0, y_1, y_2, \cdots, y_n$.

<u>Petunjuk</u>: Ujilah kebenaran kerja fungsi `panjLintasan(x, y)` yang anda buat dengan memanggilnya dan menyediakan nilai-nilai argumen <i>list</i> `x` dan <i>list</i> `y` yang sesuai. Bandingkan hasil perhitungan $L$ yang dikembalikan fungsi tersebut dengan yang diperoleh kalau menggunakan kalkulator ilmiah.
```
# panjLintasan(x, y): Menghitung panjang keseluruhan lintasan  𝐿  seusai rumus  (1) . Argumen-argumen  𝑥  dan  𝑦  
#                     masing-masing berupa lists yang berisikan nilai-nilai koordinat  𝑥0,𝑥1,𝑥2,⋯,𝑥𝑛  dan  𝑦0,𝑦1,𝑦2,⋯,𝑦𝑛 .
#                     Finandi 18/10/2021


# Judul Program
print('Panjang lintasan')
print('----------------')

# Memasukkan variable yang dibutuhkan
listX = [0, 1, 2, 3, 4]
listY = [0, 2, 4, 8, 16]

# Mendefinisikan fungsi panjLintasan(x, y)
def panjLintasan(x, y):
    L=0
    i=1
    
    # Menjalankan program dengan kalang
    while i in range(1, len(x)):
        L += ((x[i] - x[i-1])**2 + (y[i] - y[i-1])**2)**0.5
        i += 1
    return L

# Menampilkan hasil fungsi
print('Panjang lintasan dari suatu lintasan (path) =', panjLintasan(listX, listY))
```
   
Nilai $\pi$ adalah sama dengan keliling suatu lingkaran yang berjejari $\frac{1}{2}$. Umpamakan keliling ini didekati dengan suatu poligon yang melintasi $n + 1$ titik pada suatu lingkaran (mirip seperti gambar di bawah ini). 

![poligon-lingkaran.png](poligon-lingkaran.png)

Panjang dari keseluruhan lintasan poligon tersebut dapat dihitung dengan menggunakan fungsi `panjLintasan(x, y)` yang telah didefinisikan sebelumnya. Sementara, nilai-nilai koordinat $(x, y)$ dari $n + 1$ titik poligon yang mendekati lingkaran berjejari $\frac{1}{2}$ dapat dihitung dengan rumus:

$$ x_i = \frac{1}{2} \, \cos{\left( \frac{2 \, \pi \, i}{n} \right)}, \quad y_i = \frac{1}{2} \, \sin{\left( \frac{2 \, \pi \, i}{n} \right)}, \quad i = 0, 1, 2, \cdots, n \quad\quad\quad (2) $$

<span style="color:red">&#9881;</span> Dengan menggunakan fungsi `panjLintasan(x, y)` yang sudah anda buat sebelumnya; pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `piKira2.py` yang menampilkan ralat pendekatan nilai $\pi$ menggunakan cara poligon di atas dengan

$$ n = 2^k, \quad k = 2, 3, \cdots, 10 $$.
```
# piKira2.py: Menampilkan ralat pendekatan nilai  𝜋  menggunakan 
#             cara poligon di atas dengan 𝑛=2𝑘,𝑘=2,3,⋯,10
#             Finandi 21/10/2021


# Judul Program
print('        Pendekatan Terhadap  𝜋')
print('-------------------------------------')

# Memanggil pustaka & memasukkan variable
from math import pi, cos, sin
r = 1/2
K = 2*pi*r
print("|   k  | Pendekatan 𝜋 |   ralat 𝜋   |")
print("-------------------------------------")

# Menjalankan program dengan kalang
for k in range(2, 11):
    listX = []
    listY= []
    i = 0
    while i in range(2**k + 1):
        x = cos(2*pi*i/2**k)/2
        y = sin(2*pi*i/2**k)/2
        listX.append(x)
        listY.append(y)
        pendekatan = panjLintasan(listX, listY)
        galat = (K - pendekatan)/K
        i += 1
        
    # Menampilkan hasil fungsi
    print("|  %2g  |    %7g   | %11g |" % (k, pendekatan, galat))
```
    
    
### <span style="color:blue">Tugas #4: Menu Pilihan &#8594; 20 poin</span>

Suatu program komputer yang kompleks umumnya tersusun dari sejumlah bagian yang masing-masing melakukan fungsi tertentu. Untuk melaksanakan bagian yang diinginkannya, dengan papan-ketik pengguna program dapat memilih bagian program yang relevan melalui suatu menu pilihan. Sebagai contoh, program yang mengolah data secara statistik kemungkinan memiliki menu pilihan dengan isi sebagai berikut:

1. Pengambilan data dari dalam berkas
2. Penampilan grafik dari data
3. Perhitungan rerata dan simpangan baku dari data
4. Penggolongan data berdasarkan kelas-kelas dari nilainya
5. Penampilan histogram dari data
6. Pembuatan model matematika dari data
7. Pengambilan kesimpulan berdasarkan model
8. Penjelasan tentang program atau bantuan pemakaian program
9. Berhenti menggunakan program

<span style="color:red">&#9881;</span> Berdasarkan menu pilihan di atas, pada sel di bawah ini tulislahlah program Python <b>lengkap</b> bernama `MenuPilihan.py` yang melakukan langkah-langkah berikut ini:

- Menampilkan semua pilihan dalam menu dengan setiap pilihan didahului oleh huruf besar (kapital) yang berurutan.
- Menunggu pengguna program hingga ia menentukan pilihannya dengan menekan tombol papan-ketik yang sesuai dengan huruf besar di depan pilihannya.
- Menampilkan suatu <i>string</i> yang mewakili tindakan yang (seakan-akan) dilakukan program sesuai dengan pilihan pengguna.
- Jika pengguna belum memilih berhenti maka program kembali menampilkan menu pilihan dan menunggu pengguna menentukan pilihan berikutnya.

Contoh cuplikan dari tampilan program:
```
[A] Ambil data
[B] Tampilkan grafik
[C] Hitung rerata
...
[J] Selesai

Pilihan anda? B

Aksi: Program menampilkan grafik pencar (scatter plot) dari data.
```
```
# MenuPilihan.py: Melakukan langkah-langkah berikut ini
#                 -Menampilkan semua pilihan dalam menu dengan setiap pilihan didahului oleh huruf besar (kapital) yang berurutan.
#                 -Menunggu pengguna program hingga ia menentukan pilihannya dengan menekan tombol papan-ketik yang sesuai dengan huruf besar di depan pilihannya.
#                 -Menampilkan suatu string yang mewakili tindakan yang (seakan-akan) dilakukan program sesuai dengan pilihan pengguna.
#                 -Jika pengguna belum memilih berhenti maka program kembali menampilkan menu pilihan dan menunggu pengguna menentukan pilihan berikutnya.
#                 Finandi 21/10/2021


# Judul Program
print('Menu Pilihan')
print('------------')

# Menampilkan kembali contoh program yang mengolah data dengan 9 menu pilihan
print('Menu Pengolahan Data secara Statistik')
print('')
print('[A] Mengambil data')
print('[B] Menampilkan grafik')
print('[C] Menghitung rerata dan simpangan baku')
print('[D] Menggolongkan data')
print('[E] Menampilkan histogram')
print('[F] Membuat model matematika')
print('[G] Mengambil kesimpulan')
print('[H] Menjelaskan program')
print('[I] Menghentikan program')
print()

# Memasukkan variable 
x = 1

# Menjalankan program menggunakan kalang
while x > 0:
    pilihmenu= input('Masukkan menu pilihan Anda: ')
    pilihan = pilihmenu.upper()
    if pilihan == 'A':
        print('Tindakan Program: Pengambilan data dari dalam berkas.')
    elif pilihan == 'B':
        print('Tindakan Program: Penampilan grafik dari data.')
    elif pilihan == 'C':
        print('Tindakan Program: Perhitungan rerata dan simpangan baku dari data.')
    elif pilihan == 'D':
        print('Tindakan Program: Penggolongan data berdasarkan kelas-kelas dari nilainya.')
    elif pilihan == 'E':
        print('Tindakan Program: Penampilan histogram dari data.')
    elif pilihan == 'F':
        print('Tindakan Program: Pembuatan model matematika dari data.')
    elif pilihan == 'G':
        print('Tindakan Program: Pengambilan kesimpulan berdasarkan model.')
    elif pilihan == 'H':
        print('Tindakan Program: Penjelasan tentang program atau bantuan pemakaian program.')
    elif pilihan == 'I':
        x = 0
        print('Tindakan Program : Berhenti menggunakan program.')
    else:
        print('Maaf, pilihan Anda tidak tersedia. Mohon memilih menu lainnya.')
# Print kata penutup
print('Terimakasih')
```
