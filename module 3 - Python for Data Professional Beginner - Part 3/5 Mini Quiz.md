## Studi Kasus dari Senja

Di perusahaan ini, seorang analis data yang masuk umumnya berusia 21, memiliki pendapatan senilai 6.500.000 dan insentif lembur senilai 100.000. Kemudian, untuk seorang ilmuwan data yang masuk umumnya berusia 25, memiliki pendapatan senilai 12.000.000, dan insentif lembur senilai 150.000. Di sisi lain, untuk tenaga lepas, hanya terdapat pendapatan umum senilai 4.000.000 untuk pembersih data dan 2.500.000 untuk dokumenter teknis.

Berikut adalah data perusahaan beserta detail karyawan yang bekerja.

Nama Perusahaan: ABC

Alamat : Jl. Jendral Sudirman, Blok 11

Telepon : (021) 95812XX

Nama

Usia

Pekerjaan

Pendapatan

Ani

25

Pembersih Data

-

Budi

18

Dokumenter Teknis

-

Cici

-

Ilmuwan Data

-

Didi

32

Ilmuwan Data

20000000

Efi

-

Analis Data

-

Febi

28

Analis Data

12000000

Note: saat usia/pendapatan kosong maka usia/pendapatan mengikuti standar perusahaan.

“Dengan kasus ini, berarti di akhir aku harus mencetak total pengeluaran perusahaan untuk menguji kelancaranku dalam menerapkan OOP dengan Python nih,” gumamku sambil berkutat pada baris-baris kode di code editor.

Tugas:
Simulasikan dengan program yang telah dibuat.
Cetak total pengeluaran yang dimiliki perusahaan untuk menguji fungsionalitas konsep dan teknik polymorphism yang diterapkan.

Jawaban :
#Definisikan class Karyawan sebagai parent class
class Karyawan:
def **init**(self, nama, usia, pendapatan, insentif_lembur):
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

# Definisikan class TenagaLepas sebagai child class dari class Karyawan

class TenagaLepas(Karyawan):
def **init**(self, nama, usia, pendapatan):
super().**init**(nama, usia, pendapatan, 0)
def tambahan_proyek(self, nilai_proyek):
self.pendapatan_tambahan += nilai_proyek \* 0.01

#Definisikan class AnalisData sebagai child class dari class Karyawan
class AnalisData(Karyawan):
def **init**(self, nama, usia = 21, pendapatan = 6500000,
insentif_lembur = 100000):
super().**init**(nama, usia, pendapatan, insentif_lembur)

#Definisikan class IlmuwanData sebagai child class dari class Karyawan
class IlmuwanData(Karyawan):
def **init**(self, nama, usia = 25, pendapatan = 12000000,
insentif_lembur = 150000):
super().**init**(nama, usia, pendapatan,insentif_lembur)
def tambahan_proyek(self, nilai_proyek):
self.pendapatan_tambahan += 0.1 \* nilai_proyek

#Definisikan class PembersihData sebagai child class dari class TenagaLepas
class PembersihData(TenagaLepas):
def **init**(self, nama, usia, pendapatan = 4000000):
super().**init**(nama, usia, pendapatan)

#Definisikan class DokumenterTeknis sebagai child class dari class TenagaLepas
class DokumenterTeknis(TenagaLepas):
def **init**(self, nama, usia, pendapatan = 2500000):
super().**init**(nama, usia, pendapatan)

#Definisikan class Perusahaan
class Perusahaan:
def **init**(self, nama, alamat, nomor_telepon):
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
def total_pengeluaran(self):
pengeluaran = 0
for karyawan in self.list_karyawan:
pengeluaran += karyawan.total_pendapatan()
return pengeluaran
def cari_karyawan(self, nama_karyawan):
for karyawan in self.list_karyawan:
if karyawan.nama == nama_karyawan:
return karyawan
return None

# Create object karyawan sesuai dengan tugasnya masing-masing

# seperti yang dinyatakan dalam tabel.

ani = PembersihData('Ani',25)
budi = DokumenterTeknis('Budi',18)
cici = IlmuwanData('Cici')
didi = IlmuwanData('Didi',32,20000000)
efi = AnalisData('Efi')
febi = AnalisData('Febi',28,12000000)

# Create object perusahaan

perusahaan = Perusahaan('ABC','Jl. Jendral Sudirman, Blok 11','(021) 95812XX')

# Aktifkan setiap karyawan yang telah didefinisikan

perusahaan.aktifkan_karyawan(ani)
perusahaan.aktifkan_karyawan(budi)
perusahaan.aktifkan_karyawan(cici)
perusahaan.aktifkan_karyawan(didi)
perusahaan.aktifkan_karyawan(efi)
perusahaan.aktifkan_karyawan(febi)

# Cetak keseluruhan total pengeluaran perusahaan

print(perusahaan.total_pengeluaran())
