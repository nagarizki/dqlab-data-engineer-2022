## Polymorphism pada Python - Part 1

Selain dapat mendefinisikan ulang nilai dari atribut yang diwarisi oleh parent class seperti pada contoh di atas, aku juga dapat juga dapat mendefinisikan ulang fungsi yang telah diwarisi oleh parent class.

Saat aku mendefinisikan kembali fungsi yang telah diwarisi oleh parent class, secara tidak langsung aku telah menerapkan salah satu mekanisme yang secara khusus pada paradigma OO disebut dengan istilah polymorphism.

Tugas:
Aku menerapkan Polymorphism dengan mengetik potongan kode berikut pada Live Code Editor

Aku melakukan pemanggilan konstruktur class Karyawan, menerapkan polymorphism dengan mendefinisikan kembali fungsi lembur() pada AnalisData, dan menambahkan 10% tambahan pendapatan pada class AnalisData

fungsi lembur() pada objek aksara sebagai bagian dari class AnalisData akan menambahkan total_pendapatan milik objek sebesar 850000 (10% dari pendapatannya) mengikuti definisi dari fungsi lembur() pada class AnalisData

akan menghasilkan output: 9350000.

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
super().\_\_init\_\_(nama, usia, pendapatan) # menerapkan polymorphism dengan mendefinisikan kembali fungsi # lembur() pada class AnalisData
def lembur(self): # pendapatan tambahan pada class AnalisData sebesar # 10 % dari pendapatannya.
self.pendapatan_tambahan += int(self.pendapatan \* 0.1)
\# Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())

## Polymorphism pada Python - Part 2

Pada konsep inheritance, melalui fungsi super(), selain dapat mengakses constructor milik parent class, child class juga dapat mengakses atribut/fungsi yang dimiliki oleh parent class.

Tugas:
Aku menggunakan potongan kode berikut dan mengetiknya pada Live Code Editor:

akan menghasilkan output: 9175000

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
def \_\_init**(self, nama, usia, pendapatan):
super().\_\_init\_\_(nama, usia, pendapatan) # mendefinisikan kembali fungsi lembur() pada class AnalisData
def lembur(self): # memanggil fungsi lembur pada class Karyawan
super().lembur() # pendapatan tambahan pada class AnalisData sebesar # 5 % dari pendapatannya.
self.pendapatan_tambahan += int(self.pendapatan \* 0.05)
\# Buat objek karyawan yang bekerja sebagai AnalisData
aksara = AnalisData('Aksara', 25, 8500000)
aksara.lembur()
print(aksara.total_pendapatan())

## Tugas Praktek

Info: Predefined code telah diperbarui pada tanggal 25 April 2022, pastikan kode yang telah ditulis disesuaikan kembali.
Aku tak pernah membayangkan diriku benar-benar mengerjakan program untuk kebutuhan perusahaan. Seperti sekarang, aku sedang mengerjakan rikues untuk memenuhi penghitungan pembayaran fee karyawan lepas.

Tapi tak apa. Sejak program yang terakhir berhasil, aku sedikit lebih percaya diri untuk menjawab tantangan baru.

Sembari menyeruput kopi hangat, aku mulai memasukkan informasi yang cukup untuk membuat class Tenaga Lepas berisi nama, usia, dan pendapatan selama bergabung di sebuah proyek. Lalu, apa lagi ya?

“Nja, mau nanya. Kalau karyawan lepas, insentif tambahannya dari uang lembur juga?”

“Engga, Aksara. Di kantor kita, karyawan lepas dapat insentif dari proyek yang dikerjakan. Kalau hasilnya sukses bisa dapat 1% dari nilai proyek.”

“Oke,” aku mencatat itu sebagai penghitungan akhir dan mulai menulis kodenya.

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
def tambahan_proyek(self,jumlah_tambahan):
self.pendapatan_tambahan += jumlah_tambahan
def total_pendapatan(self):
return self.pendapatan + self.pendapatan_tambahan
\# Definisikan class TenagaLepas sebagai child class dari
\# class Karyawan
class TenagaLepas(Karyawan):
def \_\_init**(self, nama, usia, pendapatan):
super().\_\_init\_\_(nama, usia, pendapatan, 0)
def tambahan_proyek(self, nilai_proyek):
self.pendapatan_tambahan += int(nilai_proyek \* 0.01)

## Tugas Praktek

Info: Predefined code telah diperbarui pada tanggal 25 April 2022, pastikan kode yang telah ditulis disesuaikan kembali.
Di luar sudah menggelap. Gerobak nasi goreng yang biasanya menunggu di depan kantor tiap pukul tujuh sudah tampak. Aku masih saja larut dalam pekerjaan.

“Masih di sini, Aksara? Belum pulang?” tegur Senja yang baru saja keluar dari ruangan.

“Masih ngurusin proyek Tenaga Lepas. Ini baru dapat rikues lagi untuk nambahin class yang merepresentasikan masing-masing pekerjaan di divisi ini.”

“Hmm, kamu pakai konsep inherintance saja, akan lebih mudah,” saran Senja sebelum pulang. Sejujurnya, aku juga mau pulang. Teringat kasur di rumah yang siap untuk rebahan. Kalau begitu, pekerjaan ini harus cepat diselesaikan.

Di divisiku ada empat bidang pekerjaan, mulai dari analisis data, ilmuwan data, pembersih data, dan dokumenter teknis. Setiap peran punya sistem penerimaan fee yang berbeda. Ini yang bikin rumit. Misalnya, ilmuwan data akan mendapat insentif tambahan sebesar 10% dari proyek yang dikerjakan, dan dokumenter teknis adalah satu-satunya peran yang tidak menerima insentif dari proyek.

Oke, tenang. Ini pasti bisa, tinggal masukkin saja variabelnya satu persatu. Semangat! batinku sembari ditemani suara abang nasi goreng yang menjajakan makanannya.

Aku kembali bekerja dengan data dan kode-kode ini di code editor.

Jawaban:
\# Definisikan class Karyawan sebagai parent class
class Karyawan:
def \_\_init**(self, nama, usia, pendapatan, insentif_lembur):
self.nama = nama
self.usia = usia
self.pendapatan = pendapatan
self.pendapatan_tambahan = 0
self.insentif_lembur = insentif_lembur
def lembur(self):
self.pendapatan_tambahan += self.insentif_lembur
def tambahan_proyek(self,jumlah_tambahan):
self.pendapatan_tambahan += jumlah_tambahan
def total_pendapatan(self):
return self.pendapatan + self.pendapatan_tambahan
\# Definisikan class TenagaLepas sebagai child class dari
\# class Karyawan
class TenagaLepas(Karyawan):
def \_\_init**(self, nama, usia, pendapatan):
super().\_\_init\_\_(nama, usia, pendapatan, 0)
def tambahan*proyek(self, nilai_proyek):
self.pendapatan_tambahan += int(nilai_proyek * 0.01)
\# Definisikan class AnalisData sebagai child class dari
\# class Karyawan
class AnalisData(Karyawan):
pass
\# Definisikan class IlmuwanData sebagai child class dari
\# class Karyawan
class IlmuwanData(Karyawan):
def tambahan*proyek(self, nilai_proyek):
self.pendapatan_tambahan += int(0.1 * nilai_proyek)
\# Definisikan class PembersihData sebagai child class dari
\# class TenagaLepas
class PembersihData(TenagaLepas):
pass
\# Definisikan class DokumenterTeknis sebagai child class dari
\# class TenagaLepas
class DokumenterTeknis(TenagaLepas):
def tambahan_proyek(self, jumlah_tambahan):
return

## Tugas Praktek

Perusahaan ABC memiliki 3 orang karyawan baru seperti yang diberikan dalam tabel berikut:

Nama Usia Pendapatan
Budi ? ?
Didi 25 ?
Hadi ? 8000000
Aku di minta untuk mengisi tabel dengan detail sebagai berikut:

Budi berusia 21 dan pendapatan = 5000000
Didi berusia 25 dan pendapatan = 5000000
Hadi berusia 21 dan pendapatan = 8000000

Klik tombol untuk melanjutkan.

Jawaban:
class Karyawan:
nama_perusahaan = 'ABC'
insentif_lembur = 250000 # usia akan di-set nilainya menjadi 21 saat tidak # dispesifikasikan dan pendapatan akan di-set nilainya # menjadi 5000000 saat tidak dispesifikasikan
def \_\_init\_\_(self, nama, usia=21, pendapatan=5000000):
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
\# Karyawan baru pertama yang bernama Budi
karyawan_baru1 = Karyawan('Budi')
print(karyawan_baru1.nama)
print(karyawan_baru1.usia)
print(karyawan_baru1.total_pendapatan())
\# Karyawan baru ke-2 yang bernama Didi, umur 25
karyawan_baru2 = Karyawan('Didi', 25)
print(karyawan_baru2.nama)
print(karyawan_baru2.usia)
print(karyawan_baru2.total_pendapatan())
\# Karyawan baru ke-3 yang bernama Hadi, pendapatan 8000000
karyawan_baru3 = Karyawan('Hadi', pendapatan=8000000)
print(karyawan_baru3.nama)
print(karyawan_baru3.usia)
print(karyawan_baru3.total_pendapatan())
