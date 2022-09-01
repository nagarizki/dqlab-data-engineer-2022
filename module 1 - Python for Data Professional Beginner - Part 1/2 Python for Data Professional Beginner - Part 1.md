## Python Variables

Setelah mengetahui konsep sederhana dari sebuah variabel, aku diminta mencoba mendeklarasikan beberapa variabel dalam bentuk teks ataupun bilangan dan melakukan operasi yang melibatkan sekumpulan variabel.

Pada bagian ini, aku akan mengkaji variabel dan tipe data secara lebih detail. Pada pertemuan sebelumnya aku berhasil mendeklarasikan variabel dengan menggunakan ekspresi seperti:

Tips:

Dalam mendeklarasikan sebuah variabel, berilah nama yang mewakili isi dari variabel tersebut. Sebagai contoh :

## Aturan Penamaan Python Variables

Penamaan suatu variabel pada python dapat dikatakan valid selama memenuhi aturan-aturan berikut:

Nama dari sebuah variabel harus dimulai dengan huruf (a-z, A-Z) atau karakter garis bawah underscore (_) dan tidak dapat dimulai dengan angka (0-9).
Variabel hanya boleh mengandung karakter alfabet, bilangan dan underscore (a-z, A-Z, 0-9, _)
Variabel bersifat case-sensitive yang mengartikan bahwa variabel TINGGI, tinggi, dan Tinggi merujuk pada tiga variabel berbeda.
Selain dapat mendeklarasikan nilai dari suatu variabel secara baris per baris, aku juga dapat mendeklarasikan beberapa variabel dalam satu baris dengan menggunakan ekspresi seperti:

## Quiz

Temukan satu contoh pendeklarasian variabel yang tidak valid dari lima pilihan berikut.

JAWABAN

x = 10  
x, y, z = True, 1, 4.0  
x, y, z = 3, 3.0, True  
**2x = 80**  
x, y, z = False, True, True

## Temukan salah satu nama variabel yang tidak valid dari lima pilihan berikut

JAWABAN

\_TinggiBadan  
\_1unit\_  
tinggi_badan  
tinggi\_\_badan  
**Tinggi-badan**

## Tipe Data Dasar: Null, Boolean, Numeric dan Text

1. Null Type: Tipe data null dalam Python digunakan untuk menyimpan nilai kosong atau tidak ada yang dinyatakan dengan None.

2. Boolean Type: Tipe data boolean atau bool digunakan untuk menyimpan nilai kebenaran (True, False) dari suatu ekspresi logika.

3. Numeric Type: Tipe data yang digunakan untuk menyimpan data berupa angka. Terdapat dua macam tipe data numeric, yaitu int untuk menyimpan bilangan bulat (e.g.: 0, 1, 2, 404, -500, -1000) dan float untuk menyimpan bilangan riil (e.g.: 0.5, 1.01, 2.05, 4.04)

4. Text Type: Pada Python, tipe data string (str) digunakan untuk menyimpan data teks. Tipe data string dimulai dengan tanda kutip (baik kutip satu/ dua) dan diakhir dengan tanda kutip. Contoh: "Teks", "Contoh teks menggunakan Python", dan 'Teks pada Python'.

## Quiz

… merupakan sebuah tipe data yang hanya berisikan dua nilai kebenaran.

JAWABAN

Numeric  
Float  
Integer  
**Boolean**  
Text

# Quiz

Tipe data … merupakan tipe data yang dapat digunakan untuk menampung bilangan berkoma atau bilangan riil.

JAWABAN

**Float**  
Integer  
Boolean  
Text  
String

## Sequence Type – Part 1

Tipe data ini digunakan untuk menampung sekumpulan data secara terorganisir.
Bentuk dari tipe data sequence ini adalah List dan Tuple.
Pada part 1 ini, aku akan mempelajari tipe data list terlebih dahulu.

Tipe data list diawali dengan tanda kurung siku buka ( [ ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan kurung siku tutup ( ] ). Sebagai contoh:

Setiap elemen dari list memiliki indeks yang dimulai dari angka 0 dan terus bertambah satu nilainya hingga elemen terakhir dari list. Sebagai contoh:

Tipe data list bersifat mutable yang berarti setiap elemen di dalam list dapat dirubah nilainya setelah proses pendeklarasian list. Sebagai contoh:

Tugas:
Aku diberikan tugas untuk menerapkan variasi tipe data list dengan mengikuti petunjuk yang diberikan Senja. Berikut petunjuknya:

Petunjuk 1: Input data 1, 'dua', 3, 4.0, 5 ke dalam contoh_list
Petunjuk 2: Ambil Elemen pertama dari contoh_list untuk menampilkan output 1 menggunakan print statement
Petunjuk 3: Ambil Elemen ke empat dari contoh_list untuk menampilkan output 4.0 menggunakan print statement
Petunjuk 4: Input data 1, 'dua', 3, 4.0, 5 ke dalam contoh_list
Petunjuk 5: Rubah Elemen keempat dalam contoh_list menjadi 'empat'
Petunjuk 6: Tampilkan output elemen keempat yang telah dirubah tersebut menggunakan print statement

Jawaban:
contoh_list = [1, 'dua', 3, 4.0, 5]
print(contoh_list[0])
print(contoh_list[3])
contoh_list = [1, 'dua', 3, 4.0, 5]
contoh_list[3] = 'empat'
print(contoh_list[3])

## Sequence Type – Part 2

Setelah mempelajari tipe data list, aku mempelajari tipe data tuple. Tipe data tuple juga berfungsi untuk menampung sekumpulan data. Tipe data ini diawali dengan tanda kurung buka ( ( ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan tanda kurung tutup ( ) ). Sebagai contoh:

Aturan indeks dan cara mengakses elemen pada sebuah tuple serupa dengan list. Sebagai contoh:

Berbeda dengan tipe data list, tipe data tuple bersifat immutable yang berarti elemen pada tipe data tuple tidak dapat diubah setelah proses pendeklarasiannya.

Pada saat aku mengubah elemen pada tuple seperti pada kode berikut,

akan menghasilkan error di console, yaitu TypeError

Tugas:
Sekarang aku diberikan tugas untuk menerapkan variasi tipe data tuple dengan mengikuti petunjuk yang diberikan Senja:

Petunjuk 1: Input data Januari sampai dengan April ke dalam contoh_tuple
Petunjuk 2: Ambil Elemen pertama dari contoh_tuple untuk menampilkan output 1 menggunakan print statement
Petunjuk 3: Input kembali data Januari sampai dengan April ke dalam contoh_tuple
Petunjuk 4: Rubah Elemen pertama dalam contoh_tuple menjadi 'Desember'

Jawaban:  
contoh_tuple = ('Januari', "Februari", "Maret", "April")
print(contoh_tuple[0])
contoh_tuple = ('Januari', "Februari", "Maret", "April")
contoh_tuple[0] = 'Desember'

## Set Type

Serupa dengan tipe data sequence, tipe data set digunakan untuk menampung sekumpulan data dengan tipe lainnya. Terdapat dua jenis dari tipe data set yaitu, set dan frozenset.

Tipe data set diawali dengan tanda kurung buka kurawal ( { ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan tanda kurung tutup ( } ). Namun berbeda dengan tipe data sequence, seperti list, tipe data objek tidak mengizinkan adanya elemen dengan nilai yang sama dan tidak memperdulikan urutan dari elemen.

Sebagai contoh:

Akan menghasilkan output:

sedangkan pada tipe data set:

Akan menghasilkan output :

Dari kedua contoh output pada program, dapat terlihat:

Berbeda dengan tipe data set, tipe data list memperdulikan urutan dari setiap elemen saat list dideklarasikan.
Berbeda dengan list yang mengizinkan adanya duplikasi elemen, tipe data set tidak mengizinkan adanya elemen dengan nilai yang sama di dalamnya.
Keunikan dari kedua tipe data ini tentunya menjadi pengetahuan yang berguna.
Dan aku akan mempelajarinya kembali pada bagian struktur kontrol pengulangan!

Bagaimana dengan tipe data frozenset? Tipe data frozenset sebenarnya hanya merupakan set yang bersifat immutable, yang artinya setiap elemen di dalam frozenset tidak dapat diubah setelah proses deklarasinya. Untuk membuat tipe data frozenset, aku dapat merujuk potongan kode di bawah ini:

Akan menghasilkan output:

Tugas:
Sekarang aku diberikan tugas untuk menerapkan variasi set dan frozenset oleh Senja:

Tugas 1:Input data Dewi, Budi, Cici, Linda, Cici kedalam tipe data list dan tampilkan hasilnya
Tugas 2: Input data Dewi, Budi, Cici, Linda, Cici kedalam tipe data set dan tampilkan hasilnya
Tugas 3: Input data Dewi, Budi, Cici, Linda, Cici kedalam tipe data frozenset dan tampilkan hasilnya

Jawaban:
contoh_list = ['Dewi', 'Budi', 'Cici', 'Linda', 'Cici']
print(contoh_list)
contoh_set = {'Dewi', 'Budi', 'Cici', 'Linda', 'Cici'}
print(contoh_set)
contoh_frozen_set = ({'Dewi', 'Budi', 'Cici', 'Linda', 'Cici'})
print(contoh_frozen_set)

## Mapping Type

Tipe data mapping dapat digunakan untuk memetakan sebuah nilai ke nilai lainnya. Dalam Python, tipe data mapping disebut dengan istilah dictionary. Tipe data dictionary dapat dideklarasikan dengan diawali oleh tanda kurung buka kurawal ( { ), memisahkan setiap elemen di dalamnya dengan tanda koma ( , ) dan ditutup dengan tanda kurung tutup ( } ). Setiap elemen pada tipe data dictionary dideklarasikan dengan format:

"kunci" : "nilai"

Hal inilah yang membedakan tipe data mapping dengan tipe data set. Untuk lebih memperjelas tipe data mapping, aku mempelajari potongan kode berikut:

Potongan kode di atas adalah contoh pendeklarasian dari tipe data dictionary. Kemudian, bagaimana dengan cara mengakses informasi dari tipe data ini?

Dengan mencoba potongan code ini pada live code editor, maka aku akan mendapatkan output:

Untuk mengakses elemen dari sebuah dictionary, aku hanya perlu menspesifikasikan kata kunci yang terdapat dalam dictionary tersebut.

Tugas:
Menggunakan tipe data mapping, aku diminta Senja untuk menampilkan nama & pekerjaan John Doe, seorang Programmer.

Jawaban:
person = {'nama': 'John Doe', 'pekerjaan': 'Programmer'}
print(person['nama'])
print(person['pekerjaan'])

## Tugas Praktek

Ternyata seru juga! Aku jadi berniat mengembangkan program kalkulator potongan harga ini untuk beberapa barang sekaligus agar lebih fungsional. Kalau begitu, aku perlu rapikan dulu informasi setiap barang di tabel ini.

“Lalu, aku tinggal merepresentasikan semuanya ke tipe data dictionary, dengan begitu akan lebih mudah mengolahnya,” gumamku.
Aku pun mulai mendeklarasikan variabel sepatu, baju, dan celana untuk menampung informasi barang ke dalam live code editor.

Nama Barang

Harga

Diskon

Sepatu Niko

150000

30000

Baju Unikloh

80000

8000

Celana Lepis

200000

60000

Jawaban:
sepatu = {"Nama": "Sepatu Niko", "Harga": 150000, "Diskon": 30000}
baju = {"Nama": "Baju Unikloh", "Harga": 80000, "Diskon": 8000}
celana = {"Nama": "Celana Lepis", "Harga": 200000, "Diskon": 60000}

## Tugas Praktek

Setelah berhasil merepresentasikan setiap barang ke dalam tipe data dictionary dengan variabel nama, harga, dan diskon, langkahku selanjutnya adalah: mendeklarasikan list dengan nama daftar_belanja yang berisi data sepatu, baju, dan celana.

Jawaban:
sepatu = {"nama": "Sepatu Niko", "harga": 150000, "diskon": 30000}
baju = {"nama": "Baju Unikloh", "harga": 80000, "diskon": 8000}
celana = {"nama": "Celana Lepis", "harga": 200000, "diskon": 60000}
daftar_belanja = [sepatu, baju, celana]

## Tugas Praktek

Dengan data yang aku miliki, aku bisa menghitung total harga jual dengan potongan harga beserta pajak sebesar 10% dari nilai jual.

Untungnya Senja memberikan beberapa tips untuk menyelesaikan tugas ini:

Tips 1. # Data yang dinyatakan ke dalam dictionary
Tips 2. # Hitung harga masing-masing data setelah dikurangi diskon
Tips 3. # Hitung harga total
Tips 4. # Hitung harga kena pajak
Tips 5. # Cetak total_harga + total_pajak

Jawaban:

\# Data yang dinyatakan ke dalam dictionary

sepatu = {"nama": "Sepatu Niko", "harga": 150000, "diskon": 30000}
baju = {"nama": "Baju Unikloh", "harga": 80000, "diskon": 8000}
celana = {"nama": "Celana Lepis", "harga": 200000, "diskon": 60000}

\# Hitunglah harga masing-masing data setelah dikurangi diskon

harga_sepatu = sepatu["harga"] - sepatu["diskon"]
harga_baju = baju["harga"] - baju["diskon"]
harga_celana = celana["harga"] - celana["diskon"]

\# Hitung harga total

total_harga = harga_sepatu + harga_baju + harga_celana

\# Hitung harga kena pajak

total_pajak = total_harga \* 0.1

\# Cetak total_harga + total_pajak

print(total_harga + total_pajak)
