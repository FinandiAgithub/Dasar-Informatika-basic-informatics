# basic-informatics (Python) #7


### <span style="color:blue">Tugas #1: Operasi pada <i>Lists</i> &#8594; 20 poin</span>

Pada Bahasa Python, obyek <i>lists</i> merupakan penampung yang luwes yang dapat berisikan elemen-elemen dengan  tipe obyek yang berbeda-beda. Bahasa Python juga menyediakan berbagai operasi yang dapat mengolah obyek <i>lists</i> demi mencapai tujuan sang pemrogram. Operasi-operasi ini dapat berbentuk operator yang memerlukan satu atau dua operand dan dapat pula berupa metode yang dipanggil secara <i>dot notations</i>.

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `OperasiList_1.py` yang menampilkan hasil penerapan berbagai operator pada dua <i>lists</i> berikut ini:
```
s1 = [2, 1, 4, 3]
s2 = ['c', 'a', 'p']
```
Operasi yang dikenakan kepada kedua <i>lists</i> tersebut adalah

1. `s1 + s2`
2. `3 * s1 + 2 * s2`
3. `s1[1]`
4. `s1[1:3]`
5. `s1 + s2[-1]`

Pada setiap hasil operasi, berikan uraian anda yang menjelaskan cara kerja operasi terkait sehingga menimbulkan hasil seperti yang ditampilkan.
```
#OperasiList_1.py: Program yang menampilkan hasil penerapan berbagai operator pada dua lists berikut ini:
#                  s1 = [2, 1, 4, 3]
#                  s2 = ['c', 'a', 'p']
#                  Finandi 4/11/2021


# Menampilkan judul Program
print('OperasiList_1.py')
print('-----------------')

# Memasukkan variable yang dibutuhkan
s1 = [2, 1, 4, 3]
s2 = ['c', 'a', 'p']


# Operasi 1 = Penjumlahan list
a = s1 + s2
p = 'Operasi 1 bekerja dengan menjumlahkan dan menggabungkan kedua list s1 dan s2'
print('\n#Operasi 1')
print('Hasil     : ', a)
print("Penjelasan: ",p)
print()

# Operasi 2 = Penjumlahan dan perkalian list
b = 3 * s1 + 2 * s2
q = 'Operasi 2 bekerja dengan mengulang list yang ada yaitu list s1 3 kali dan list s2 2 kali'
print('#Operasi 2')
print('Hasil     : ', b)
print("Penjelasan: ",q)
print()

# Operasi 3 = Menampilkan elemen 1 pada list s1
c = s1[1]
r = 'Operasi 3 bekerja dengan menampilkan ke 1 pada list s1'
print('#Operasi 3')
print('Hasil     : ', c)
print("Penjelasan: ",r)
print()

# Operasi 4 = Menghilangkan elemen 1&3 pada list s1
d = s1[1:3]
s = 'Operasi 4 bekerja dengan menghilangkan elemen ke-1 dan ke-3 dari list s1'
print('#Operasi 4')
print('Hasil     : ', d)
print("Penjelasan: ",s)
print()

# Operasi 5 = Menggabungkan elemen list
e = s1 + [s2[-1]]
t = 'Operasi 5 bekerja dengan menggabungkan elemen list s1 dengan elemen terakhir dari list s2'
print('#Operasi 5')
print('Hasil     : ', e)
print("Penjelasan: ",t)
```

<span style="color:red">&#9881;</span> Pada sel di bawah ini, tulislah program Python <b>lengkap</b> bernama `OperasiList_2.py` yang menampilkan hasil penerapan berbagai metode pada dua <i>lists</i> berikut ini:
```
s1 = [2, 1, 4, 3]
s2 = ['c', 'a', 'p']
```
Metode yang dikenakan kepada kedua <i>lists</i> tersebut adalah seperti di bawah ini. Perlakukan setiap operasi secara mandiri atau anggaplah bahwa `s1` dan `s1` berisikan nilai-nilai aslinya sebelum penerapan setiap metode.

1. `s1.remove(2)`
2. `s1.sort()`
3. `s1.append([s2.index('b')])`
4. `s2.pop(s1.pop(2))`
5. `s2.insert(s1[0], 'd')`

Pada setiap hasil operasi, berikan uraian anda yang menjelaskan cara kerja operasi terkait sehingga menimbulkan hasil seperti yang ditampilkan.
```
# OperasiList_2.py: Program yang menampilkan hasil penerapan berbagai operator pada dua lists berikut ini:
#                   s1 = [2, 1, 4, 3]
#                   s2 = ['c', 'a', 'p']
#                   Finandi 4/11/2021


# Menampilkan judul Program
print('OperasiList_2.py')
print('----------------')

# Memasukkan variable yang dibutuhkan
s1 = [2, 1, 4, 3]
s2 = ['c', 'a', 'p']

# Operasi 1 = Remove
s1_op1 = s1.copy()
s2_op1 = s2.copy()
s1_op1.remove(2)
p = 'Operasi 1 bekerja dengan menghilangkan elemen "2" pada list s1'
print('\n#Operasi 1')
print('Hasil     :', s1_op1)
print('Penjelasan:',p)
print()

# Operasi 2 = Sort
s1_op2 = s1.copy()
s2_op2 = s2.copy()
s1_op2.sort()
q = 'Operasi 2 menjalankan perintah sort dengan hasil elemen list s1 yang berurutan dari nilai terkecil hingga terbesar'
print('#Operasi 2')
print('Hasil      :', s1_op2)
print('Penjelasan:',q)
print()

# Operasi 3 = Append, Index
s1_op3 = s1.copy()
s2_op3 = s2.copy()
r = "Operasi 3 menghasilkan output error karena perintah index mencari elemen b pada list s2,dimana dalam list s2 tidak terdapat elemen b"
print('#Operasi 3')
try:
    s1_op3.append([s2_op3.index('b')])
    print("Hasil     :", s1_op3 )
except ValueError:
    print("Penjelasan:",r)
print()

# Operasi 4 = Pop
s1_op4 = s1.copy()
s2_op4 = s2.copy()
s = "Operasi 4 menghasilkan output error karena perintah pop(s1.pop(2) menghasilkan elemen 4, elemen 4 kemudian dijadikan index pada s2.pop, sedangkan list s2 tidak cukup untuk memenuhi perintah tersebut"
print('#Operasi 4')
try:
    s2_op4.pop(s1_op4.pop(2))
    print("Hasil     :", s2_op4)
except IndexError:
    print('Penjelasan:',s)
print()

# Operasi 5 = Insert
s1_op5 = s1.copy()
s2_op5 = s2.copy()
t = "Operasi 5 bekerja dengan menginput nilai 'd' pada list s2 dengan posisi index yang sesuai dengan perintah s1[0] dimana index tersebut merujuk pada elemen 2"
s2_op5.insert(s1_op5[0], 'd')
print('#Operasi 5')
print("Hasil     :", s2_op5)
print("Penjelasan:",t)
```

