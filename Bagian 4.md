# basic-informatics (Python) #4


### <span style="color:blue">Tugas #1: Jumlah Elemen <i>List</i> &#8594; 15 poin</span>
Bahasa Python sudah menyediakan fungsi <i>built-in</i> `sum()` yang dapat menjumlahkan elemen-elemen suatu <i>list</i> yang dicantumkan sebagai argumennya ketika fungsi ini dipanggil. Sebagai contoh:
<center><tt>sum([1, 2, 3, 4])</tt> menghasilkan nilai kembalian: <tt>10</tt></center>

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah definisi fungsi buatan anda sendiri bernama `jumlahList()` yang menerima satu <i>list</i> yang berisikan bilangan bulat atau bilangan pecahan dan menghasilkan nilai kembalian berupa jumlah semua elemen di dalam <i>list</i> tersebut. Ujilah kebenaran kerja fungsi yang anda buat dengan memanggil namanya dan memberikan nilai argumen yang diperlukannya serta membandingkan dengan hasil jumlah <i>list</i> terkait menggunakan fungsi <i>built-in</i> Python: `sum()`.
```
# JumlahList.py: menerima satu list yang berisikan bilangan bulat atau bilangan pecahan dan menghasilkan 
#                nilai kembalian berupa jumlah semua elemen di dalam list tersebut
#                Finandi 28/09/2021


# Membuat definisi program
def jumlahList(l):
    total = 0
    for val in l:
        total = total + val
    return total

# Memasukkan list yang ingin dihitung
lis = [1,2,3,4]

# Menampilkan hasil program menggunakan jumlahList()
print('Hasil program menggunakan jumlahList()')
print (jumlahList(lis))

# Menampilkan hasil program menggunakan fungsi built-in sum()
print('\nHasil program menggunakan fungsi built-in sum()')
sum(lis)
```

### <span style="color:blue">Tugas #2: Fungsi Rapat Kementakan &#8594; 30 poin</span>
Pada kehidupan sehari-hari, banyak peristiwa di alam terjadi dengan frekuensi relatif yang dapat dilukiskan sebagai fungsi rapat kementakan (<i>probability density function</i>) normal. Fungsi ini memiliki bentuk kurva yang khas, yakni mirip bentuk genta atau stupa. Bentuk spesifik dari fungsi ini tergantung pada dua parameter: nilai rerata (<i>mean</i>) $\mu$ dan simpangan baku (<i>standard deviation</i>) $\sigma$. Nilai rerata menentukan kecenderungan memusat dari fungsi ini sedangkan simpangan baku menentukan kecenderungannya untuk menyebar. Untuk sejumlah nilai variabel mandiri $x$, fungsi rapat kementakan normal menimbulkan sejumlah nilai $y$ terkait yang dihubungkan dengan rumus:
$$ y(x) = \frac{1}{\sigma \, \sqrt{2 \, \pi}} \, e^{-\frac{1}{2} \left[ \frac{x - \mu}{\sigma} \right]^2} $$
dengan $e$ = 2.71828 dan $\pi$ = 3.141594.
Grafik berikut menampilkan empat bentuk fungsi rapat kementakan normal pada rentang $x$ yang sama namun dengan nilai $\mu$ dan $\sigma$ yang berbeda-beda:
![distribusi normal](normal.png)

<span style="color:red">&#9881;</span> Pada sel di bawah ini tulislah definisi fungsi `normal()` yang menerima tiga argumen: nilai rerata $\mu$, simpangan baku $\sigma$ dan nilai $x$. Fungsi ini mengembalikan nilai rapat kementakan $y$ yang sesuai dengan rumus fungsi rapat kementakan normal di atas.
```
# normal().py: Menerima tiga argumen: nilai rerata 𝜇, simpangan baku 𝜎 dan nilai 𝑥. Fungsi ini mengembalikan 
#              nilai rapat kementakan 𝑦 yang sesuai dengan rumus fungsi rapat kementakan normal di atas.
#              Finandi 28/09/2021


# Memanggil modul Math
from math import *

# Mendefinisikan fungsi
def normal(𝜇,𝜎,𝑥) :
    y = (1/(𝜎*(2*pi)**(1/2)))*(e**((-1/2)*((𝑥-𝜇)/𝜎)**2)) 
    return y
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, ujilah fungsi `normal()` yang sudah anda definisikan di atas dengan memberikan nilai-nilai argumen yang sesuai dan membandingkan nilai yang dikembalikannya dengan dua contoh berikut:
- `normal(0, 0.45, 0.25)` $\rightarrow$ 0.76
- `normal(-2, 0.71, -2)` $\rightarrow$ 0.56
```
# normal().py: Menerima tiga argumen: nilai rerata 𝜇, simpangan baku 𝜎 dan nilai 𝑥. Fungsi ini mengembalikan 
#              nilai rapat kementakan 𝑦 yang sesuai dengan rumus fungsi rapat kementakan normal di atas.
#              Finandi 28/09/2021


# Menampilkan hasil program
print('normal(0, 0.45, 0.25) = %0.2f' % normal(0, 0.45, 0.25))
print('normal(-2, 0.71, -2) = %0.2f' % normal(-2, 0.71, -2))
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python __lengkap__ bernama `TabelNormal.py` yang menghitung dan menampilkan secara rapi suatu tabel yang terdiri dari 5 kolom:
- kolom pertama berisikan nilai-nilai `x` yang terentang dari -5 hingga +5 dengan lompatan sebesar 0.25,
- kolom kedua berisikan nilai-nilai `y` yang dihitung dari fungsi rapat kementakan normal dengan nilai `x`pada kolom pertama serta $\mu$ = 0 dan $\sigma^2$ = 0.2,
- kolom ketiga berisikan nilai-nilai `y` yang dihitung dari fungsi rapat kementakan normal dengan nilai `x` pada kolom pertama serta $\mu$ = 0 dan $\sigma^2$ = 1,
- kolom keempat berisikan nilai-nilai `y` yang dihitung dari fungsi rapat kementakan normal dengan nilai `x` pada kolom pertama serta $\mu$ = 0 dan $\sigma^2$ = 5.0,
- kolom kelima berisikan nilai-nilai `y` yang dihitung dari fungsi rapat kementakan normal dengan nilai `x` pada kolom pertama serta $\mu$ = -2 dan $\sigma^2$ = 0.5.
Gunakanlah fungsi `normal()` yang sudah anda definisikan dan ujikan sebelumnya. Bandingkan isi tabel yang dihasilkan dengan tampilan grafik di atas. Tampilkan nilai-nilai real dengan kecermatan satu angka di belakang titik desimal.
```
# TabelNormal.py: Menghitung dan menampilkan secara rapi suatu tabel yang terdiri dari 5 kolom
#                 Finandi 28/09/2021


# Membuat List kosong untuk nilai x
nilai_x = []
# Membuat variabel
x = -5
dx = 0.25
# Membuat kalang untuk mengisi list
while x <= 5 :
    nilai_x.append(x)
    x += dx

# Membuat variabel
𝜇 = 0
𝜎 = 0.2**(1/2) 
# Membuat List kosong untuk nilai y1
y_1 = [] 
# Membuat kalang untuk mengisi list
for i in nilai_x :
    y1 = normal(𝜇,𝜎,i)
    y_1.append(y1) 

# Membuat variabel
𝜇 = 0
𝜎 = 1**(1/2)
# Membuat List kosong untuk nilai y2
y_2 = []
# Membuat kalang untuk mengisi list
for i in nilai_x :
    y2 = normal(𝜇,𝜎,i)
    y_2.append(y2) 

# Membuat variabel
𝜇 = 0
𝜎 = 5**(1/2) 
# Membuat List kosong untuk nilai y3
y_3 = [] 
# Membuat kalang untuk mengisi list
for i in nilai_x :
    y3 = normal(𝜇,𝜎,i)
    y_3.append(y3)

# Membuat variabel
𝜇 = -2
𝜎 = 0.5**(1/2) 
# Membuat List kosong untuk nilai y4
y_4 = [] 
# Membuat kalang untuk mengisi list
for i in nilai_x :
    y4 = normal(𝜇,𝜎,i)
    y_4.append(y4)

# Menampilkan hasil program dalam bentuk tabel
print('         Tabel Normal        ')
print('------------------------------')    
print('|  X  |  Y1 |  Y2 |  Y3 | Y4 |')        
print('------------------------------')    
for i in range(len(nilai_x)):
    X = nilai_x[i]
    Y1 = y_1[i] 
    Y2 = y_2[i] 
    Y3 = y_3[i]
    Y4 = y_4[i]
    print('|%3.1f | %2.1f | %2.1f | %2.1f | %2.1f|' %(X, Y1, Y2, Y3, Y4))
```
