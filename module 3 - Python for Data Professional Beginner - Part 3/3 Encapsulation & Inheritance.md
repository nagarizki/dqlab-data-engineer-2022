## Encapsulation pada Python – Part 2

Pada contoh di atas, terlihat bahwa atribut nama pada setiap objek dapat diakses secara bebas di luar scope dari sebuah class. Agar suatu properti ataupun fungsi dari sebuah class tidak dapat diakses secara bebas di luar scope milik suatu class, aku dapat mendefinisikan access modifier (level akses) saat sebuah atribut/fungsi didefinisikan.

Terdapat 2 macam access modifier dalam Python, yakni.

Public access: dapat aku definisikan dengan secara langsung menuliskan nama dari atribut/ fungsi. Dalam sebuah objek, atribut/fungsi yang bersifat public access dapat diakses di luar scope sebuah class
Private access: dapat aku definisikan dengan menambahkan double underscore (\_\_) sebelum menuliskan nama dari atribut/fungsi. Dalam sebuah objek, atribut/fungsi yang bersifat private access hanya dapat diakses di dalam scope sebuah class.

Tugas:
Untuk memperkuat pemahamanku terkait konsep enkapsulasi dalam paradigma OO, aku menggunakan contoh syntax dan mengetiknya pada live code editor:

Pada potongan kode di atas, atribut nama_perusahaan bersifat public yang mengartikan bahwa aku dapat mengakses atribut ini di luar scope class Karyawan.

tidak akan menyebabkan error dan menghasilkan output: ABC

Kemudian, atribut **nama, **usia, **pendapatan_tambahan, **insentif_lembur dan pendapatan bersifat private sehingga atribut ini hanya dapat diakses di dalam scope class Karyawan.

Saat aku mencoba mengakses atribut-atribut ini di luar scope class Karyawan, Python akan mengembalikan error yang menyatakan bahwa class Karyawan tidak memiliki atribut tersebut. Sebagai contoh,

akan menyebabkan error yang menyatakan bahwa objek Karyawan tidak memiliki atribut \_\_nama.

Jawaban:
\# Definisikan class Karyawan
class Karyawan:
nama_perusahaan = 'ABC'
**insentif_lembur = 250000
def \_\_init**(self, nama, usia, pendapatan):
self.**nama = nama
self.**usia = usia
self.**pendapatan = pendapatan
self.**pendapatan_tambahan = 0
def lembur(self):
self.**pendapatan_tambahan += self.**insentif_lembur
def tambahan_proyek(self, insentif_proyek):
self.**pendapatan_tambahan +=insentif_proyek
def total_pendapatan(self):
return self.**pendapatan + self.**pendapatan_tambahan
\# Buat objek karyawan bernama Aksara
aksara = Karyawan('Aksara', 25, 8500000)
\# Akses ke attribute class Karyawan
print(aksara.\_\_class**.nama_perusahaan)
\# Akan menimbulkan error ketika di run
print(aksara.\_\_nama)

## Inheritance pada Python – Part 1

Inheritance adalah salah satu mekanisme di konsep OO yang mengizinkan aku untuk mendefinisikan sebuah class baru berdasarkan class yang sebelumnya telah dideklarasikan.

Melalui konsep inheritance, sebuah class baru dapat memiliki atribut dan fungsi pada class yang sebelumnya telah didefinisikan. Pada konsep inheritance, atribut/fungsi yang akan diwariskan hanyalah atribut/fungsi dengan access modifier public, atribut/fungsi dengan access modifier private tidak akan diturunkan.

Tugas:
Definisikan class Karyawan pada Live Code Editor:

melakukan inheritance (menurunkan seluruh atribut dan fungsi dari class Karyawan) ke class AnalisData

melakukan inheritance (menurunkan seluruh atribut dan fungsi dari class Karyawan) ke class IlmuwanData

objek AnalisData dapat mengakses fungsi lembur milik class Karyawan

akan menghasilkan output: 8750000

Selanjutnya,

objek IlmuwanData dapat mengakses fungsi tambahan_proyek milik class Karyawan

akan menghasilkan output: 15000000

Penjelasan:
Melalui potongan kode di atas, aku telah menerapkan konsep inheritance. Melalui konsep inheritance class AnalisData dan IlmuwanData akan memiliki setiap atribut dan fungsi yang dimiliki oleh class Karyawan (Hal ini dikarenakan seluruh atribut dan fungsi dari class Karyawan bersifat public).

Pada konsep inheritance, class AnalisData dan class IlmuwanData disebut sebagai child class dari class Karyawan; sehingga class Karyawan dapat disebut sebagai parent class dari class AnalisData dan IlmuwanData.

Suatu child class dapat mengakses atribut ataupun fungsi yang dimiliki oleh parent class dengan menggunakan fungsi super(). Pada contoh di atas, fungsi super() digunakan oleh child class (AnalisData dan IlmuwanData) untuk mengakses constructor yang dimiliki oleh parent class (Karyawan).

Catatan: Sebenarnya, aku tidak perlu mendefinisikan kembali fungsi (termasuk constructor) ataupun properti yang memiliki public access modifier di sebuah child class. Python akan secara otomatis mewariskan seluruh fungsi dan properti dengan public access modifier ke sebuah child class. Contoh potongan kode di atas hanya diperkenankan untuk mencontohkan penggunaan fungsi super().

Jawaban:
\# Definisikan class Karyawan (sebagai base class)
class Karyawan:
nama_perusahaan = 'ABC'
insentif_lembur = 250000
def \_\_init**(self, nama, usia, pendapatan):
self.nama = nama
self.usia = usia
self.pendapatan = pendapatan
self.pendapatan_tambahan = 0
def lembur(self):
self.pendapatan_tambahan += self.insentif_lembur
def tambahan_proyek(self, insentif_proyek):
self.pendapatan_tambahan += insentif_proyek
def total_pendapatan(self):
return self.pendapatan + self.pendapatan_tambahan
\# Buat class turunan (sebagai inherit class) dari class karyawan,
\# yaitu class AnalisData
class AnalisData(Karyawan):
def \_\_init**(self, nama, usia, pendapatan): # melakukan pemanggilan konstruktur class Karyawan
super().\_\_init**(nama, usia, pendapatan)
\# Buat kembali class turunan (sebagai inherit class) dari class karyawan,  
\# yaitu class IlmuwanData
class IlmuwanData(Karyawan):
def \_\_init**(self, nama, usia, pendapatan): # melakukan pemanggilan konstruktur class Karyawan
super().\_\_init\_\_(nama, usia, pendapatan)
\# Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())
\# Buat objek karyawan yang bekerja sebagai IlmuwanData
senja = IlmuwanData('Senja', 28, 13000000)
senja.tambahan_proyek(2000000)
print(senja.total_pendapatan())

## Inheritance pada Python – Part 2

Pada bagian pertama aku telah mempelajari bagaimana child class mewarisi fungsi/atribut dari parent class dengan menggunakan fungsi super(). Melalui konsep inheritance, child class dapat memodifikasi atribut/ fungsi yang diwarisi oleh sebuah parent class dengan mendefinisikan ulang atribut/ fungsi menggunakan nama yang sama.

Tugas:
Aku mencoba contoh berikut dengan Live Code Editor

Fungsi lembur pada objek aksara sebagai bagian dari class AnalisData akan menambahkan total_pendapatan milik objek sebesar 250000 mengikuti insentif_lembur milik class Karyawan

akan menghasilkan output: 8750000

Selanjutnya,

fungsi lembur pada objek senja sebagai bagian dari class IlmuwanData akan menambahkan total_pendapatan milik objek sebesar 500000 dikarenakan class IlmuwanData telah mendefinisikan kembali nilai insentif lembur menjadi 500000

akan menghasilkan output: 13500000

Jawaban:
\# Definisikan class Karyawan (sebagai base class)
class Karyawan:
nama_perusahaan = 'ABC'
insentif_lembur = 250000
def \_\_init**(self, nama, usia, pendapatan):
self.nama = nama
self.usia = usia
self.pendapatan = pendapatan
self.pendapatan_tambahan = 0
def lembur(self):
self.pendapatan_tambahan += self.insentif_lembur
def tambahan_proyek(self, insentif_proyek):
self.pendapatan_tambahan += insentif_proyek
def total_pendapatan(self):
return self.pendapatan + self.pendapatan_tambahan
\# Buat class turunan (sebagai inherit class) dari class karyawan,
\# yaitu class AnalisData
class AnalisData(Karyawan):
def \_\_init**(self, nama, usia, pendapatan): # melakukan pemanggilan konstruktur class Karyawan
super().\_\_init**(nama, usia, pendapatan)
\# Buat kembali class turunan (sebagai inherit class) dari class karyawan,  
\# yaitu class IlmuwanData
class IlmuwanData(Karyawan): # mengubah atribut insentif_lembur yang digunakan pada fungsi lembur()
insentif_lembur = 500000
def \_\_init**(self, nama, usia, pendapatan):
super().\_\_init\_\_(nama, usia, pendapatan)
\# Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())
\# Buat objek karyawan yang bekerja sebagai IlmuwanData
senja = IlmuwanData('Senja', 28, 13000000)
senja.lembur()
print(senja.total_pendapatan())

##
