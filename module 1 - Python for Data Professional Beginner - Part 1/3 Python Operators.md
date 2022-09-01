## Pendahuluan

Setelah aku berhasil mempelajari detail terkait dengan variables dan data type, sekarang aku akan mempelajari operator-operator yang tersedia di dalam Python. Di dalam Python, operator terbagi ke dalam 6 kelompok:

Arithmetic operators
Assignment operators
Comparison operators
Logical operators
Identity operators
Membership operators

## Arithmetic Operators

Operator arithmetic digunakan pada tipe data numerik, untuk melakukan operasi matematika sederhana yang terdiri atas:

Simbol Operator

Keterangan

Contoh

-

Penambahan

3 + 2 akan menghasilkan output: 5

-

Pengurangan

4 - 2 akan menghasilkan output: 2

-

Perkalian

3 \* 2 akan menghasilkan output: 6

/

Pembagian

3 / 2 akan menghasilkan output: 1.5

%

Modulo/sisa bagi

3 % 2 akan menghasilkan output: 1

dikarenakan 3 tidak habis dibagi 2 dan menyisakan 1

8 % 2 akan menghasilkan output: 0

dikarenakan 8 habis dibagi 2

\*\*

Pangkat

3 \*\* 2 akan menghasilkan output: 9

//

Pembagian dengan pembulatan ke bawah

3 // 2 akan menghasilkan output: 1

dikarenakan 1.5 akan menjadi 1 saat dibulatkan ke bawah.

## Assignment Operators

Operator assignment digunakan untuk mendeklarasikan nilai secara langsung ke suatu variabel.

Simbol Operator

Keterangan

Contoh

+=

Penambahan

x = 3

x += 2 ekivalen dengan x = x + 2

akan mengubah nilai x menjadi 5

-=

Pengurangan

x = 3

x -= 2 ekivalen dengan x = x - 2

akan mengubah nilai x menjadi 1

\*=

Perkalian

x = 3

x _= 2 ekivalen dengan x = x _ 2

akan mengubah nilai x menjadi 6

/=

Pembagian

x = 3

x /= 2 ekivalen dengan x = x / 2

akan mengubah nilai x menjadi 1.5

%=

Modulo/sisa bagi

x = 3

x %= 2 ekivalen dengan x = x % 2

akan mengubah nilai x menjadi 1

\*\*=

Pangkat

x = 3

x **= 2 ekivalen dengan x = x ** 2

akan mengubah nilai x menjadi 9

//=

Pembagian dengan pembulatan ke bawah

x = 3

x //= 2 sama dengan x = x // 2

akan mengubah nilai x menjadi 1

## Quiz

Berdasarkan kode berikut:

bil1 = 5
bil2 = bil1 // 2
print(bil2)
Jika dijalankan berapakah hasilnya?

JAWABAN

1  
1.5  
**2**  
2.5  
3

## Quiz

Berdasarkan kode berikut:

bil1 = 5
bil2 = bil1 % 2
bil1 \*= bil2
print(bil1)
Jika dijalankan berapakah hasilnya?

JAWABAN

0
1
**5**
10
50

## Comparison Operators

Operator comparison dapat digunakan untuk membandingkan dua buah nilai, berikut merupakan contoh-contoh operator komparasi.

Simbol Operator

Keterangan

Contoh

==

Persamaan

33 == 33 akan menghasilkan output: True dikarenakan benar 33 sama dengan 33

34 == 33 akan menghasilkan output: False dikarenakan 34 tidak sama dengan 33

!=

Pertidaksamaan

34 != 33 akan menghasilkan output: True dikarenakan benar bahwa 34 tidak sama dengan 33

33 != 33 akan menghasilkan output: False dikarenakan 33 sama dengan 33

>

Lebih besar dari

34 > 33 akan menghasilkan output: True dikarenakan 34 lebih besar dari 33

33 > 34 akan menghasilkan output False dikarenakan tidak benar 33 lebih besar dari 34

<

Lebih kecil dari

33 < 34 akan menghasilkan output True dikarenakan benar 33 lebih kecil dari 34

34 < 33 akan menghasilkan output: False dikarenakan tidak benar 34 lebih kecil dari 33

> =

Lebih besar atau sama dengan

34 >= 33 akan menghasilkan output True dikarenakan 34 lebih besar dari 33

34 >= 34 akan menghasilkan output True dikarenakan 34 sama dengan 34

33 >= 34 akan menghasilkan output False dikarenakan 33 tidak lebih besar dari 34 dan tidak sama dengan 34

<=

Lebih kecil atau sama dengan

33 <= 34 akan menghasilkan output True dikarenakan 33 lebih kecil dari 34

33 <= 33 akan menghasilkan output True dikarenakan 34 sama dengan 33

34 <= 33 akan menghasilkan output False dikarenakan 34 tidak lebih kecil dari 33 dan tidak sama dengan 34

## Logical Operators

Operator logical digunakan untuk menggabungkan beberapa nilai kebenaran atas suatu statemen logika.

Simbol Operator

Keterangan

Contoh

and

dan - menerima dua nilai kebenaran dan mengembalikan nilai benar jika keduanya benar

x = 5

x >= 1 and x <= 10

akan mengembalikan nilai True

x = 5

x >= 1 and x <= 4

akan mengembalikan nilai False

or

atau - menerima dua nilai kebenaran dan mengembalikan nilai benar jika salah satu benar

x = 3

x >= 1 or x <= 2

akan mengembalikan nilai True dikarenakan statemen logika pertama terpenuhi

x = 3

x >= 5 or x <= 0

akan mengembalikan nilai False dikarenakan kedua statemen logika tidak terpenuhi (bernilai False)

not

negasi - menerima sebuah nilai kebenaran dan mengembalikan komplemennya

x = 7

not(x == 7) akan mengembalikan nilai False

not(x >= 10) akan mengembalikan nilai True

## Quiz

Lengkapilah program Python berikut agar menghasilkan output True:

bil1 = 5
bil2 = \_\_\_
print(bil2 > bil1 and bil2 < 15)
JAWABAN

0  
1  
5  
**10**  
50

## Quiz

Lengkapilah program Python berikut agar menghasilkan output False:

bil1 = 5
bil2 = bil1 // 2
hasil = \_\_\_
print(hasil)
JAWABAN

bil1 == 1 or bil1 > bil2  
bil1 >= 5 and bil2 == 2  
bil1 != 5 or bil2 != 5  
**bil1 <= bil2 or bil1 == 2**  
bil1 == bil2 or bil2 == 2

## Identity Operators

Operator identitas dapat digunakan untuk membandingkan identitas dari dua buah variabel.

Simbol Operator

Keterangan

Contoh

is

Menerima dua buah objek dan mengembalikan nilai True ketika keduanya merujuk pada objek yang sama dan False dalam kondisi lainnya

x = ["Ani", "Budi"]

y = ["Ani", "Budi"]

a = x

print(a is x) akan menampilkan nilai True dikarenakan a dan x merujuk ke objek yang sama

print(a is y) akan menampilkan nilai False dikarenakan a dan y tidak merujuk ke objek yang sama meskipun isi di dalam keduanya sama.

is not

Menerima dua buah objek dan mengembalikan nilai True ketika keduanya merujuk pada objek yang berbeda dan False jika sama

x = ["Ani", "Budi"]

y = ["Ani", "Budi"]

a = x

print(a is not x) akan menampilkan nilai False dikarenakan a dan x merujuk ke objek yang sama

print(a is not y) akan menampilkan nilai True dikarenakan a dan y tidak merujuk ke objek yang sama

Pada umumnya, operator identitas sering digunakan bersamaan dengan fungsi type(), yang mana fungsi type() akan menerima sebuah objek dan mengembalikan tipe data dari objek tersebut. Di bawah ini adalah contoh penggunaan operator identitas dan fungsi type().

Nah, aku coba mempraktekkan contoh tutorial yang diberikan Senja pada live code editor.

akan menampilkan pesan True.

Setelah line di bawah ini selesai dieksekusi, Python akan secara otomatis mengubah tipe data dari x menjadi float

akan menampilkan pesan False, dan

akan menampilkan pesan True

Klik tombol Next untuk melanjutkan.

## Membership Operators

Operator keanggotaan (membership) dapat digunakan untuk memeriksa anggota dari sebuah tipe data sequence/set. Operator keanggotaan meliputi:

Simbol Operator

Keterangan

Contoh

in

Menerima sebuah sequence/set dan objek, mengembalikan True ketika objek merupakan anggota dari sequence/set, dan False ketika bukan.

x = ["Ani", "Budi", "Cici"]

y = "Cici"

z = "Dodi"

print(y in x) akan menampilkan nilai True

print(z in x) akan menampilkan nilai False

not in

Menerima sebuah sequence/set dan objek, mengembalikan True ketika objek bukan merupakan anggota dari sequence/set, dan False ketika merupakan.

x = ["Ani", "Budi", "Cici"]

y = "Cici"

z = "Dodi"

print(y not in x) akan menampilkan nilai False

print(z not in x) akan menampilkan nilai True

## Nilai Prioritas Operator dalam Python – Part 1

Info: materi telah diperbarui pada tanggal 29 Januari 2022, pastikan kembali kode yang telah ditulis disesuaikan dengan bagian Lesson.

Setelah mempelajari berbagai operator dalam bahasa pemrograman Python, tentunya aku juga ingin bisa menuliskan operasi-operasi variabel yang bersifat ekspresif dan ringkas.

Sebagai contoh, untuk menuliskan sebuah program menghitung diskon dan pajak pembelian berdasarkan ilmu yang telah aku pelajari, aku dapat menuliskannya dengan potongan kode berikut:

Setelah aku memberikan potongan kode yang telah kubuat, ternyata Senja memiliki ide yang lebih baik. Wajar saja, Senja adalah mentorku. Senja langsung mencontohkan cara lebih mudah dengan menjelaskan presedensi (urutan eksekusi) dari operator.

Dengan mengikuti masukan Senja, aku dapat menuliskannya ke dalam jumlah baris yang lebih sedikit seperti pada potongan kode berikut

Tugas:
Aku diminta Senja untuk menghitung harga yang harus dibayarkan menggunakan barang senilai 150,000, dengan diskon 30% dan pajak 10%, menggunakan cara yang aku gunakan awal dan cara lebih singkat yang diajarkan Senja.

Jawaban:

\# Kode awal
total*harga = 150000
potongan_harga = 0.3
pajak = 0.1 # pajak dalam persen ~ 10%
harga_bayar = 1 - potongan_harga # baris pertama
harga_bayar *= total*harga # baris kedua
pajak_bayar = pajak * harga*bayar # baris ketiga
harga_bayar += pajak_bayar # baris ke-4
print("Kode awal - harga_bayar=", harga_bayar)
\# Penyederhanaan baris kode dengan menerapkan prioritas operator
total_harga = 150000
potongan_harga = 0.3
pajak = 0.1 # pajak dalam persen ~ 10%
harga_bayar = (1 - potongan_harga) * total*harga #baris pertama
harga_bayar += harga_bayar * pajak # baris kedua
print("Penyederhanaan kode - harga_bayar=", harga_bayar)

## Nilai Prioritas Operator dalam Python – Part 2

Dalam bahasa pemrograman Python, tabel berikut mencakup nilai prioritas dan arah pengerjaan dari setiap operator.

Operator

Nilai Prioritas

Arah pengerjaan

Deskripsi

()

10

Kiri ke kanan

Grouping

x[index]

9

Kiri ke kanan

Mengakses elemen array

\*\*

8

Kanan ke kiri

pangkat

+x

-x

7

Kiri ke kanan

Tanda bilangan positif dan negatif

-

/

%

6

Kiri ke kanan

Perkalian Pembagian Modulus

-

*

5

Kiri ke kanan

Penambahan Pengurangan

is, is not, in, not in

<=, <, >=, >

==, !=

4

Kiri ke kanan

Membership operator Comparison Operator

not

3

Kiri ke kanan

Operator logika negasi (not)

and

2

Kiri ke kanan

Operator logika konjungsi (and)

or

1

Kiri ke kanan

Operator logika disjungsi (or)

Dari tabel di atas, dapat terlihat bahwa tanda () memiliki nilai prioritas yang paling tinggi. Hal itu menandakan jika di dalam suatu statemen yang melibatkan beberapa operator secara sekaligus, setiap operasi yang berada di dalam tanda () akan dikerjakan terlebih dahulu.
Kemudian, jika terdapat beberapa operasi dalam tanda (), tanda kurung yang berada di sebelah paling kiri akan dikerjakan terlebih dahulu dikarenakan arah pengerjaan dari tanda () adalah dari kiri ke kanan.

Sebagai contoh, pada proses deklarasi variabel nilai di bawah ini.

Dari contoh di atas, meskipun operator perkalian (\*) memiliki nilai prioritas yang lebih tinggi dari operator pengurangan (-), tanda () akan membuat Python mengerjakan bagian pengurangan terlebih dahulu, sebelum akhirnya mengalikan hasil pengurangan dengan bilangan 100.

## Quiz

Untuk kode di bawah ini, Python akan menampilkan pesan:

bilangan = (5 % 3 \*_ 2) + (3 + 2 _ 2) \* (4 - 2)
print(bilangan)

JAWABAN

28  
26  
**19**  
30  
24

## Tugas Praktek

Senja memang hebat!

Aku baru sadar, dengan struktur penulisan yang tepat maka penulisan syntax dapat dipersingkat untuk menjadi lebih simpel.

Kenapa tidak terpikirkan olehku, ya? Harusnya aku tidak perlu mendeklarasikan variabel total_pajak dan aku bisa langsung menampung hasil perhitungan akhir saat mendeklarasikan variabel total_harga. Jadi, kodeku akan berjalan jika aku menambahkan setiap harga barang yang telah dipotong diskon sebelum menghitung pajak.

Tugas:
Dengan cara yang diajarkan Senja, aku akan membuat potongan kode diatas menjadi lebih simpel. Jangan lupa ada pajak 10%.

Jawaban:

sepatu = { "nama" : "Sepatu Niko", "harga": 150000, "diskon": 30000 }
baju = { "nama" : "Baju Unikloh", "harga": 80000, "diskon": 8000 }
celana = { "nama" : "Celana Lepis", "harga": 200000, "diskon": 60000 }
harga_sepatu = sepatu\["harga"\] - sepatu\["diskon"\]
harga_baju = baju\["harga"\] - baju\["diskon"\]
harga_celana = celana\["harga"\] - celana\["diskon"\]
total_harga = (harga_sepatu + harga_baju + harga_celana) \* 1.1
print(total_harga)
