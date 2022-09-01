## Class dan Objek dalam Python - Part 3

Berkaitan dengan kedua jenis atribut yang telah aku pelajari, aku menggunakan contoh berikut untuk memperkuat pemahamanku terkait dengan konsep class attribute.

Class Karyawan pada umumnya memiliki beberapa atribut seperti nama, usia, pendapatan serta nama perusahaan di mana karyawan tersebut bekerja. Untuk merepresentasikan diriku dan Senja sebagai karyawan yang bekerja di sebuah perusahaan yang sama (anggap saja perusahan ABC), aku dapat merepresentasikan dengan menggunakan konsep class attribute

Menggunakan potongan kode di atas, nama_perusahaan sebagai class attribute dapat kita akses dengan menggunakan syntax:

akan menghasilkan output: ABC

Kemudian, sesuai dengan konsep yang telah aku pelajari sebelumnya, saat aku mengubah nilai atribut yang merupakan sebuah class attribute, nilai dari atribut akan berubah untuk seluruh objek.

Saat perusahaan berubah nama, misalkan nama perusahaan berubah dari 'ABC' ke 'DEF', dikarenakan atribut nama_perusahaan merupakan sebuah class attribute, aku hanya cukup mengganti nama_perusahaan pada salah satu objek saja (tidak perlu mengganti nama_perusahaan milik seluruh objek). Contohnya:

akan menghasilkan output: DEF

Dengan merubah nama perusahaan, maka nama perusahaan milik objek Senja juga secara otomatis berubah menjadi DEF.

Tugas:
Aku di minta untuk mengerjakan tutorial sederhana untuk membantu memahami konsep OOP:

Definisikan Class Karyawan
Inisiasi object yang dinyatakan dalam variabel Aksara dan Senja
Cetak Nama Perusahaan melalui penggunaan keyword \_\_class\_\_
Ubah Nama Perusahaan menjadi 'DEF'

Jawaban:
\# Definisikan class Karyawan
class Karyawan:
nama_perusahaan = 'ABC'
\# Inisiasi object yang dinyatakan dalam variabel aksara dan senja
aksara = Karyawan()
senja = Karyawan()
\# Cetak nama perusahaan melalui penggunaan keyword \_\_class**
\# pada class attribute nama_perusahaan
print(aksara.\_\_class**.nama_perusahaan)
\# Ubah nama_perusahaan menjadi 'DEF'
aksara.\_\_class**.nama_perusahaan = 'DEF'
\# Cetak nama_perusahaan objek aksara dan senja
print(aksara.\_\_class**.nama_perusahaan)
print(senja.\_\_class\_\_.nama_perusahaan)

## Class dan Objek dalam Python - Part 4

Pada bagian sebelumnya aku telah mempelajari contoh deklarasi class Karyawan; nama, usia dan pendapatan karyawan adalah contoh dari konsep instance attribute. Hal ini dikarenakan setiap karyawan tentunya dapat memiliki nama, usia dan pendapatan yang berbeda.

Tugas:
Untuk merepresentasikan instance attribute milik Aksara, aku mengetik potongan kode berikut pada live code editor:

menghasilkan output:

Aksara, Usia 25, Pendapatan: 8500000
Selanjutnya, untuk merepresentasikan instance attribute milik Senja, aku mengetik potongan kode berikut pada live code editor:

menghasilkan output:

Senja, Usia 28, Pendapatan: 12500000

Penjelasan:
Dari potongan kode di atas, atribut nama, usia dan pendapatan merupakan contoh dari instance variabel. Sebagai tambahan, fungsi **init**() di dalam class Karyawan secara khusus disebut sebagai constructor. Melalui sebuah constructor, aku dapat meng-assign (menginisialisasi) atribut-atribut milik sebuah objek.

Pada bahasa pemrograman Python, setiap fungsi (termasuk constructor) akan menerima dirinya sendiri (self) sebagai parameter pertama dari fungsi. Kemudian, aku dapat menambahkan parameter-parameter lain setelah parameter self sesuai dengan kebutuhan. Seperti pada contoh di atas, saat objek dibuat (diinisialisasi), aku dapat melemparkan nama, usia dan pendapatan melalui syntax,

aksara = Karyawan('Aksara', 25, 8500000)
Terakhir, aku belajar bahwa objek aksara dan senja diizinkan untuk memiliki nama, usia dan pendapatan yang berbeda. Untuk mengakses instance attribute dalam sebuah class, aku perlu menuliskan sintaks self diikuti dengan tanda titik (.) sebelum nama atribut.

Jawaban:
\# Definisikan class Karyawan
class Karyawan:
nama_perusahaan = 'ABC'
def \_\_init\_\_(self, nama, usia, pendapatan):
self.nama = nama
self.usia = usia
self.pendapatan = pendapatan
\# Buat object bernama aksara dan senja
aksara = Karyawan('Aksara', 25, 8500000)
senja = Karyawan('Senja', 28, 12500000)
\# Cetak objek bernama aksara
print(aksara.nama + ', Usia: ' + str(aksara.usia) + ', Pendapatan ' + str(aksara.pendapatan))
\# Cetak objek bernama senja
print(senja.nama + ', Usia: ' + str(senja.usia) + ', Pendapatan ' + str(senja.pendapatan))

## Behavior pada Class

Selain dapat mendefinisikan atribut, dalam sebuah class, aku diperbolehkan untuk mendefinisikan fungsi-fungsi (behavior) dari sebuah class.

Dari potongan kode yang telah aku gunakan, aku dapat menambahkan fungsi-fungsi berkaitan dengan class Karyawan. Sebagai contoh, seorang karyawan tentunya mungkin saja memiliki pendapatan tambahan berdasarkan banyaknya kerja lembur dan jumlah proyek yang telah diselesaikan.

Tugas:
Untuk menghitung pendapatan tambahan dari jumlah kerja lembur dan jumlah proyek yang diselesaikan oleh seorang karyawan dan mengakses pendapatan total dari seorang karyawan, aku dapat menuliskan potongan kode berikut.

untuk menambahkan pendapatan lembur diriku, aku dapat menggunakan fungsi lembur() pada objek aksara.

untuk menambahkan pendapatan tambahan proyek pada senja, aku dapat mengakses fungsi tambahan_proyek() pada objek senja

Selanjutnya, aku dapat menghitung total pendapatanku dan Senja

Layaknya proses pendefinisian fungsi pada Python, fungsi-fungsi dalam sebuah class juga dapat memiliki parameter (seperti fungsi tambahan_proyek dalam contoh) ataupun mengembalikan sebuah nilai (seperti fungsi total_pendapatan dalam contoh).

Jawaban:
\# Definisikan class Karyawan berikut dengan attribut dan fungsinya
class Karyawan:
nama_perusahaan = 'ABC'
insentif_lembur = 250000
def \_\_init\_\_(self, nama, usia, pendapatan):
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
\# Buat object dari karwayan bernama Aksara dan Senja
aksara = Karyawan('Aksara', 25, 8500000)
senja = Karyawan('Senja', 28, 12500000)
\# Aksara melaksanakan lembur
aksara.lembur()
\# Senja memiliki proyek tambahan
senja.tambahan_proyek(2500000)
\# Cetak pendapatan total Aksara dan Senja
print('Pendapatan Total Aksara: ' + str(aksara.total_pendapatan()))
print('Pendapatan Total Senja: ' +str(senja.total_pendapatan()))

## Tugas Praktek

Seperti biasa, aku selalu pusing setiap usai membaca teori data. “Gimana, Aksara?” tanya Senja tanpa memalingkan perhatian dari laptop.

“Kayaknya butuh praktik deh,” sahutku.

“Oke, ini coba kamu bikin sistem manajemen perusahaan sederhana pakai Object Oriented (OO) ya. Artinya dalam program ini kamu harus mampu memuat informasi nama, alamat, nomor telepon, dan daftar karyawan yang bekerja. Satu lagi, jangan lupa masukkan fungsi untuk mengaktifkan dan menonaktifkan karyawan.”

“Siap. Ini aku masukkan informasi class karyawan juga kali yah?” tanyaku sembari bersiap-siap memasukkan kode dan mendaftar informasi karyawan secara lebih rapi, mulai dari nama, usia, pendapatan tetap, tambahan, dan insentif lembur.

“Bagus juga itu. Bikin saja pendapatan mula-mula karyawannya bernilai 0, lalu bisa bertambah oleh fungsi lembur dan fungsi tambahan proyek sebagai parameter dan variabel pendapatan tambahan karyawan.”

Aku mengangguk dan siap bertempur. Terakhir aku menyelipkan fungsi untuk menghitung total pendapatan. Ini paling penting, hehehe.

Tugas:
Lengkapi class Karyawan dan class Perusahaan menggunakan potongan kode pada Live Code Editor.

Jawaban:
\# Definisikan class Karyawan
class Karyawan:
def \_\_init**(self, nama, usia, pendapatan, insentif_lembur):
self.nama = nama
self.usia = usia
self.pendapatan = pendapatan
self.pendapatan_tambahan = 0
self.insentif_lembur = insentif_lembur
def lembur(self):
self.pendapatan_tambahan += self.insentif_lembur
def tambahan_proyek(self, jumlah_tambahan):
self.pendapatan_tambahan += jumlah_tambahan
def total_pendapatan(self):
return self.pendapatan + self.pendapatan_tambahan
\# Definisikan class Perusahaan
class Perusahaan:
def \_\_init**(self, nama, alamat, nomor_telepon):
self.nama = nama
self.alamat = alamat
self.nomor_telepon = nomor_telepon
self.list_karyawan = []
def aktifkan_karyawan(self, karyawan):
self.list_karyawan.append(karyawan)
def nonaktifkan_karyawan(self, nama_karyawan):
karyawan_nonaktif = None
for karyawan in self.list_karyawan:
if karyawan.nama == nama_karyawan:
karyawan_nonaktif = karyawan
break
if karyawan_nonaktif is not None:
self.list_karyawan.remove(karyawan_nonaktif)

## Tugas Praktek

Sekitar satu jam lebih berkutat depan laptop, kode aku kelar juga! Tapi, sebelum kutunjukkan pada Senja, lebih baik aku coba simulasikan dulu. Kuambil post-it kuning di ujung meja dan kugambar tabel berisi daftar perusahaan dan karyawan sebagai contoh, lengkap dengan pendapatan tetap dan tambahan yang diterima.

Nama Perusahaan: ABC

Alamat : Jl. Jendral Sudirman, Blok 11

No. Telp : (021) 95205XX

Nama Pekerja

Usia

Pendapatan

Insentif Lembur

Ani

25

8500000

100000

Budi

28

12000000

150000

Cici

30

15000000

200000

Kalau sudah seperti ini, tinggal dimasukkan saja ke variabel list_karyawan, lalu operasikan. “Programnya berhasil!” batinku.

Tanpa kusadari ada tepukan halus di pundakku, itu dari Senja yang ternyata sedari tadi diam-diam memerhatikan hasil kerjaku.

“Nice try, Aksara.” Aku memandang puas dengan hasil kodeku kali ini.

Jawaban:
class Karyawan:
def \_\_init\_\_(self, nama, usia, pendapatan, insentif_lembur):
self.nama = nama
self.usia = usia
self.pendapatan = pendapatan
self.pendapatan_tambahan = 0
self.insentif_lembur = insentif_lembur
def lembur(self):
self.pendapatan_tambahan += self.insentif_lembur
def tambahan_proyek(self, jumlah_tambahan):
self.pendapatan_tambahan += jumlah_tambahan
def total_pendapatan(self):
return self.pendapatan + self.pendapatan_tambahan

class Perusahaan:
def \_\_init\_\_(self, nama, alamat, nomor_telepon):
self.nama = nama
self.alamat = alamat
self.nomor_telepon = nomor_telepon
self.list_karyawan = []
def aktifkan_karyawan(self, karyawan):
self.list_karyawan.append(karyawan)
def nonaktifkan_karyawan(self, nama_karyawan):
karyawan_nonaktif = None
for karyawan in self.list_karyawan:
if karyawan.nama == nama_karyawan:
karyawan_nonaktif = karyawan
break
if karyawan_nonaktif is not None:
self.list_karyawan.remove(karyawan_nonaktif)

\# Definisikan perusahaan
perusahaan = Perusahaan('ABC', 'Jl. Jendral Sudirman, Blok 11', '(021) 95205XX')
\# Definisikan nama-nama karyawan
karyawan_1 = Karyawan('Ani', 25, 8500000, 100000)
karyawan_2 = Karyawan('Budi', 28, 12000000, 150000)
karyawan_3 = Karyawan('Cici', 30, 15000000, 200000)
\# Aktifkan karyawan di perusahaan ABC
perusahaan.aktifkan_karyawan(karyawan_1)
perusahaan.aktifkan_karyawan(karyawan_2)
perusahaan.aktifkan_karyawan(karyawan_3)
