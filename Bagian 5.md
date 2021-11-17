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

1. Gunakan rumus berikut:

    $$ \text{nomorHari} = 31 \times (bulan - 1) + tanggal $$
<p>
2. Jika bulan dari hari tersebut adalah setelah Februari maka sesuaikan $\text{nomorHari}$ (yang diperoleh pada langkah 1) dengan mengurangkan

    $$ (4 \times bulan + 23) \, / \, 10 $$
<p>
3. Jika tahun dari hari tersebut adalah tahun kabisat dan hari tersebut ternyata adalah setelah 29 Februari maka sesuaikan $\text{nomorHari}$ (yang diperoleh pada langkah 2) dengan menambahkan $1$.
<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `nomorHari.py` yang menampilkan nomor hari dari suatu hari yang diberikan pengguna program melalui papan-ketik. Pada awal pelaksanaan program, pengguna diminta untuk memberikan tanggal, bulan dan tahun dari hari yang ingin ditentukan nomornya.
<u>Petunjuk</u>: Untuk menentukan apakah tahun dari hari yang ingin ditentukan nomornya adalah termasuk tahun kabisat maka manfaatkan program bernama `TahunKabisat.py` yang telah anda buat pada <b>Kerja #1</b> dalam berkas `LabPDI-05-888888.ipynb`.

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
  
