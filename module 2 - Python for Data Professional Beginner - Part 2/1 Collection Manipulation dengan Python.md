## Apa itu Collection Manipulation?

Collections manipulation adalah salah satu teknik yang penting untuk dikuasai setiap programmer. Melalui penguasaan materi collections manipulation, aku dapat mengolah berbagai tipe data collections dalam Python yang meliputi:

list,
tuple,
set, dan
Dictionary.

## Mengakses List dan Tuple – Part 1

Seperti yang telah aku pelajari pada modul Python for Data Professional Beginner - Part 1: Bab “Sequence Type”, aku dapat mengakses elemen pada suatu list ataupun tuple dengan menggunakan indeks atau semacam nomor urut dari list atau tuple tersebut. Indeks pada suatu tipe data list atau tuple dimulai dari angka 0.

Tugas 1:
Aku mencoba mempraktekkan potongan kode di bawah dengan live code editor:

Untuk menampilkan output Januari dan Juni, yang aku lakukan adalah mengetikkan syntax sederhana seperti berikut:

Kemudian, untuk mengakses elemen dari belakang pada suatu list/tuple, aku juga dapat menggunakan indeks negatif pada list/tuple.

Tugas 2:
Untuk menampilkan output Desember dan November, yang aku lakukan adalah mengetikkan syntax sederhana sebagai berikut:

Jawaban:
bulan_pembelian = ('Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni', 'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember')
print(bulan_pembelian[0])
print(bulan_pembelian[5])
print(bulan_pembelian[-1])
print(bulan_pembelian[-2])

## Mengakses List dan Tuple – Part 2

Cara collections manipulation pertama yang akan aku pelajari adalah memotong (slicing) list/tuple dengan menggunakan rentangan nilai indeks (range of index).

Tugas 1:
Aku mencoba mempraktekkan potongan kode di bawah dengan live code editor:

Untuk menampilkan output bulan_pembelian Mei, Juni, Juli, Agustus, aku dapat menggunakan syntax di bawah untuk mengambil index 4 - 7.

Tugas 2:
Untuk menampilkan output bulan_pembelian Januari, Februari, Maret, April, Mei aku dapat menggunakan syntax di bawah untuk mengambil index 0 - 4.

Tugas 3:
Untuk menampilkan output September, Oktober, November, Desember. Aku dapat menggunakan syntax di bawah untuk mengambil index 8 - elemen terakhir.

Tugas 4:
Aku juga dapat memotong suatu list/tuple dengan menggunakan indeks negatif. Sebagai contoh untuk mendapatkan output September, Oktober, November aku bisa menggunakan syntax di bawah:

Jawaban:
bulan_pembelian = ('Januari', 'Februari', 'Maret', 'April', 'Mei', 'Juni', 'Juli', 'Agustus', 'September', 'Oktober', 'November', 'Desember')
pertengahan_tahun = bulan_pembelian[4:8]
print(pertengahan_tahun)
awal_tahun = bulan_pembelian[:5]
print(awal_tahun)
akhir_tahun = bulan_pembelian[8:]
print(akhir_tahun)
print(bulan_pembelian[-4:-1])

## Penggabungan Dua atau Lebih List atau Tuple

Selain dapat melakukan pemotongan terhadap tipe data list/tuple, aku juga dapat menggabungkan isi dari suatu list (ataupun tuple) dengan list lainnya (atau dengan tuple lainnya) dengan menggunakan operator penambahan (+).

Tugas:
Aku menggunakan potongan kode yang dicontohkan dengan live code editor:

Akan menghasilkan output:

Jawaban:
list_makanan = ['Gado-gado', 'Ayam Goreng', 'Rendang']
list_minuman = ['Es Teh', 'Es Jeruk', 'Es Campur']
list_menu = list_makanan + list_minuman
print(list_menu)

## List Manipulation – Part 1

Untuk memanipulasi tipe data list, aku dapat menggunakan sekumpulan fitur yang telah tersedia dalam bahasa pemrograman Python. Merujuk pada tabel di bawah, aku dapat memahami fitur-fitur untuk melakukan manipulasi data yang terdiri atas append(), clear(), copy(), count() dan extend()

Fitur

Keterangan

Contoh Penggunaan

.append()
Menambahkan data sebagai elemen terakhir di list

akan menghasilkan output:

.clear()
Menghapus seluruh elemen dalam sebuah list

akan menghasilkan output berupa empty list

.copy()
Mengembalikan copy dari setiap elemen dalam list

melalui penggunaan fitur copy() penambahan pada list_makanan2 tidak akan mempengaruhi list_makanan1

melalui operator assignment =, penambahan pada list_makanan3 akan mempengaruhi list_makanan1

Kita akan cetak isi list_makanan1

akan menghasilkan output:

['Gado-gado', 'Ayam Goreng', 'Rendang', 'Ketoprak']
Sementara itu, list_makanan2 akan dicetak dengan

akan menghasilkan output:

['Gado-gado', 'Ayam Goreng', 'Rendang', 'Opor']
.count()
Mengembalikan jumlah kemunculan suatu elemen pada list

akan menampilkan output:

.extend()
Menggabungkan dua buah list seperti penggunaan operator + untuk list

akan menghasilkan output:

Jawaban:
\# Fitur .append()
print(">>> Fitur .append()")
list_makanan = ['Gado-gado', 'Ayam Goreng', 'Rendang']
list_makanan.append('Ketoprak')
print(list_makanan)
\# Fitur .clear()
print(">>> Fitur .clear()")
list_makanan = ['Gado-gado', 'Ayam Goreng', 'Rendang']
list_makanan.clear()
print(list_makanan)
\# Fitur .copy()
print(">>> Fitur .copy()")
list_makanan1 = ['Gado-gado', 'Ayam Goreng', 'Rendang']
list_makanan2 = list_makanan1.copy()
list_makanan3 = list_makanan1
list_makanan2.append('Opor')
list_makanan3.append('Ketoprak')
print(list_makanan1)
print(list_makanan2)
\# Fitur .count()
print(">>> Fitur .count()")
list_score = ['Budi', 'Sud', 'Budi', 'Budi', 'Budi', 'Sud', 'Sud']
score_budi = list_score.count('Budi')
score_sud = list_score.count('Sud')
print(score_budi) # akan menampilkan output 4
print(score_sud) # akan menampilkan output 3
\# Fitur .extend()
print(">>> Fitur .extend()")
list_menu = ['Gado-gado', 'Ayam Goreng', 'Rendang']
list_minuman = ['Es Teh', 'Es Jeruk', 'Es Campur']
list_menu.extend(list_minuman)
print(list_menu)

## List Manipulation – Part 2

Selanjutnya aku akan mempelajari fitur index(), insert(), pop(), remove(), reverse(), dan sort() untuk melakukan manipulasi.

Tugas:
Ketikkanlah kode yang diberikan pada contoh penggunaan di live code editor.

Fitur

Keterangan

Contoh Penggunaan

.index()
Mengembalikan indeks dari elemen pertama yang ditemukan dari awal sebuah list

akan menampilkan output:

.insert()
Menyisipkan elemen pada indeks yang dispesifikasikan

akan menampilkan output

.pop()
Menghilangkan elemen pada posisi tertentu

akan menghasilkan output:

.remove()
Menghilangkan elemen dengan nilai tertentu

akan menghasilkan output:

.reverse()
Membalik urutan elemen dari sebuah list

akan menghasilkan output:

.sort()
Mengurutkan elemen pada sebuah list, secara default dengan urutan dari kecil ke besar (ascending).

akan menghasilkan output:

melakukan proses pengurutan dari besar ke kecil (descending)

akan menghasilkan output:

Jawaban:
\# Fitur .index()
print(">>> Fitur .index()")
list_score = \['Budi','Sud','Budi','Budi','Budi','Sud','Sud'\]
score_pertama_sud = list_score.index('Sud') + 1
print(score_pertama_sud) # akan menampilkan output 2
\# Fitur .insert()
print(">>> Fitur .insert()")
list_score = \['Budi','Sud','Budi','Budi','Sud'\]
list_score.insert(3, 'Sud')
print(list_score)
\# Fitur .pop()
print(">>> Fitur .pop()")
list_menu = \['Gado-gado', 'Ayam Goreng', 'Rendang'\]
list_menu.pop(1)
print(list_menu)
\# Fitur .remove()
print(">>> Fitur .remove()")
list_menu = \['Gado-gado', 'Ayam Goreng', 'Rendang', 'Ketoprak'\]
list_menu.remove('Rendang')
print(list_menu)
\# Fitur .reverse()
print(">>> Fitur .reverse()")
list_menu = \['Gado-gado', 'Ayam Goreng', 'Rendang', 'Ketoprak'\]
list_menu.reverse()
print(list_menu)
\# Fitur .sort()
print(">>> Fitur .sort()")
list_menu = \['Gado-gado', 'Ayam Goreng', 'Rendang', 'Ketoprak'\]
list_menu.sort() # Default: Ascending
print(list_menu)
list_menu.sort(reverse = TRUE) # Descending
print(list_menu)

## Tuple Manipulation

Aku juga mempelajari fitur yang dapat digunakan untuk melakukan manipulasi data dengan tipe data tuple.

Tugas:
Ketikkan potongan kode berikut pada live code editor:

Fitur

Keterangan

Contoh Penggunaan

.count()
Mengembalikan jumlah kemunculan suatu elemen pada tuple

akan menampilkan output 4

akan menampilkan output 3

.index()
Mengembalikan indeks dari elemen pertama yang ditemukan dari awal sebuah tuple

indeks dimulai dari 0

Akan menampilkan output 2

Jawaban:
\# Fitur .count()
print(">>> Fitur .count()")
tuple_score = ('Budi', 'Sud', 'Budi', 'Budi', 'Budi', 'Sud', 'Sud')
score_budi = tuple_score.count('Budi')
score_sud = tuple_score.count('Sud')
print(score_budi) # akan menampilkan output 4
print(score_sud) # akan menampilkan output 3
\# Fitur .index()
print(">>> Fitur .index()")
tuple_score = ('Budi','Sud','Budi','Budi','Budi','Sud','Sud')
score_pertama_sud = tuple_score.index('Sud')+1
print(score_pertama_sud) # akan menampilkan output 2

## Set Manipulation – Part 1

Sedikit berbeda dengan tipe data list dan tuple, pada tipe data set terdapat cukup banyak fitur yang disediakan oleh bahasa Python.

Tugas:
Ketikkan potongan kode pada kolom Contoh Penggunaan di live code editor.

Fitur

Keterangan

Contoh Penggunaan

.add()
Menambahkan data ke dalam set. Penting untuk kita ingat bahwa pada tipe data set tidak mengizinkan adanya duplikasi elemen di dalamnya.

mungkin dapat menghasilkan output:

Perlu diingat bahwa: tipe data set merupakan unordered collection setiap kali perintah print dijalankan, aku mungkin akan melihat output yang berbeda.

.clear()
Menghapus seluruh elemen dalam sebuah set

akan menghasilkan output:

atau empty set {}.

.copy()
Mengembalikan copy dari setiap elemen dalam set

serupa dengan tipe data list, melalui operator assignment =, penambahan pada set_buah2 akan mempengaruhi set_buah1

melalui penggunaan fitur copy() penambahan pada set_buah2 tidak akan mempengaruhi set_buah1

menghasilkan output:

dan

menghasilkan output:

.update()
Menambahkan elemen dari suatu set dengan set lainnya.

menambahkan parcel1 dengan elemen-elemen dari parcel2

menghasilkan output:

.pop()
Menghilangkan elemen dari sebuah set secara acak.

menghasilkan output:

> > > Fitur .pop()
> > > 'Anggur' atau 'Apel' ataupun 'Jeruk'
> > > dan

menghasilkan output:

{'Apel','Jeruk'} atau {'Anggur','Jeruk'} ataupun {'Apel','Anggur'}
.remove()
Menghilangkan elemen dengan nilai tertentu

menghasilkan output:

Jawaban:

\# Fitur .add()

print(">>> Fitur .add()")
set_buah = {'Jeruk','Apel','Anggur'}
set_buah.add('Melon')
print(set_buah)

\# Fitur .clear()

print(">>> Fitur .clear()")
set_buah = {'Jeruk','Apel','Anggur'}
set_buah.clear()
print(set_buah)

\# Fitur .copy()

print(">>> Fitur .copy()")
set_buah1 = {'Jeruk','Apel','Anggur'}
set_buah2 = set_buah1
set_buah3 = set_buah1.copy()
set_buah2.add('Melon')
set_buah3.add('Kiwi')
print(set_buah1)
print(set_buah2)

\# Fitur .update()

print(">>> Fitur .update()")
parcel1 = {'Anggur','Apel','Jeruk'}
parcel2 = {'Apel','Kiwi','Melon'}
parcel1.update(parcel2)
print(parcel1)

\# Fitur .pop()

print(">>> Fitur .pop()")
parcel = {'Anggur','Apel','Jeruk'}
buah = parcel.pop()
print(buah)
print(parcel)

\# Fitur .remove()

print(">>> Fitur .remove()")
parcel = {'Anggur','Apel','Jeruk'}
parcel.remove('Apel')
print(parcel)

## Set Manipulation – Part 2

Sedikit berbeda dengan tipe data list dan tuple, pada tipe data set terdapat cukup banyak fitur manipulasi yang bisa aku gunakan.

Tugas:
Ketikkan potongan kode yang diberikan pada Contoh Penggunaan pada live code editor:

Fitur

Keterangan

Contoh Penggunaan

.union()
Mengembalikan hasil penggabungan (union) dari dua buah set.

perhatikan bahwa fungsi union mengembalikan hasil penggabungan setiap elemen milik set parcel1 dan parcel2 nilai dari set parcel1 tidak akan berubah melalui fitur union() tidak seperti fitur update()

menghasilkan output:

dan

menampilkan output:

.isdisjoint()
Mengembalikan nilai kebenaran apakah suatu set disjoint (saling lepas/tidak mengandung elemen yang sama) dengan set lainnya.

akan menghasilkan output True dikarenakan parcel1 dan parcel2 tidak mengandung elemen yang sama

akan menghasilkan output False dikarenakan parcel1 dan parcel3 sama-sama memiliki Apel

.issubset()
Mengembalikan nilai kebenaran apakah sebuah set merupakan subset dari set lainnya. Sebuah set A merupakan subset dari set B jika seluruh elemen dari set A merupakan bagian dari set B.

akan menghasilkan output True dikarenakan Anggur dan Apel terdapat dalam set parcel_C

akan menghasilkan output False dikarenakan Durian dan Semangka tidak terdapat dalam set parcel_C

.issuperset()
Mengembalikan nilai kebenaran apakah sebuah set merupakan superset dari set lainnya. Sebuah set A merupakan superset dari set B jika seluruh elemen dari set B terkandung dalam set A.

parcel_A, parcel_B, dan parcel_C seperti yang diberikan pada baris fitur .issubset()

akan menghasilkan output True dikarenakan C mengandung seluruh elemen dari set A

akan menghasilkan output False dikarenakan C tidak mengandung seluruh elemen dari set B

.intersection()
Mengembalikan sebuah set yang merupakan intersection dari dua set lainnya.

dapat menghasilkan output:

dikarenakan Apel dan Jeruk terdapat baik pada set parcel_A dan parcel_B.

.difference()
Mengembalikan sebuah set yang berisikan difference dari dua set lainnya. Difference dari sebuah set A berdasarkan set B adalah setiap elemen yang terdapat di set A tetapi tidak terdapat di set B.

parcel_A dan parcel_B merupakan set yang sama dengan baris fitur .intersection()

dapat menghasilkan output:

.symmetric_difference()
Mengembalikan sebuah set yang berisikan symmetric difference dari dua set lainnya. Symmetric difference dari sebuah set A dan B adalah setiap elemen dari set A yang tidak terdapat di set B digabungkan dengan (union) setiap elemen dari set B yang tidak terdapat di set A.

dapat menghasilkan output:

Jawaban:
\# Fitur .union()
print(">>> Fitur .union()")
parcel1 = {'Anggur','Apel','Jeruk'}
parcel2 = {'Apel','Kiwi','Melon'}
parcel3 = parcel1.union(parcel2)
print(parcel1)
print(parcel3)
\# Fitur .isdisjoint()
print(">>> Fitur .isdisjoint()")
parcel1 = {'Anggur','Apel','Jeruk'}
parcel2 = {'Kiwi','Melon','Pisang'}
parcel3 = {'Apel','Srikaya','Semangka'}
parcel1_parcel2_disjoint = parcel1.isdisjoint(parcel2)
print(parcel1_parcel2_disjoint)
parcel1_parcel3_disjoint = parcel1.isdisjoint(parcel3)
print(parcel1_parcel3_disjoint)
\# Fitur .issubset()
print(">>> Fitur .issubset()")
parcel_A = {'Anggur', 'Apel'}
parcel_B = {'Durian','Semangka','Apel'}
parcel_C = {'Anggur', 'Kiwi', 'Apel', 'Jeruk', 'Melon'}
parcel_A_dalam_C = parcel_A .issubset(parcel_C)
parcel_B_dalam_C = parcel_B.issubset(parcel_C)
print(parcel_A_dalam_C)
print(parcel_B_dalam_C)
\# Fitur .issuperset()
print(">>> Fitur .issuperset()")
parcel_C_mengandung_A = parcel_C.issuperset(parcel_A)
parcel_C_mengandung_B = parcel_C.issuperset(parcel_B)
print(parcel_C_mengandung_A)
print(parcel_C_mengandung_B)
\# Fitur .intersection()
print(">>> Fitur .intersection()")
parcel_A = {'Anggur', 'Kiwi', 'Apel', 'Jeruk', 'Melon'}
parcel_B = {'Apel', 'Jeruk', 'Semangka', 'Durian', 'Tomat'}
parcel_C = parcel_A.intersection(parcel_B)
print(parcel_C)
\# Fitur .difference()
print(">>> Fitur .difference()")
parcel_C = parcel_A.difference(parcel_B)
print(parcel_C)
\# Fitur .symmetric_difference()
print(">>> Fitur .symmetric_difference()")
parcel_A = {'Anggur', 'Apel', 'Jeruk', 'Melon'}
parcel_B = {'Apel','Jeruk','Semangka','Leci'}
parcel_C = parcel_A.symmetric_difference(parcel_B)
print(parcel_C)

## Dictionary Manipulation

Aku baru saja selesai mengerjakan beberapa kuis latihan ketika Senja mengejutkanku dengan tepukannya di belakang pundakku.

“Lagi apa kamu, Aksara?”

“Ngagetin aja, Nja.”

“Soalnya serius banget. Padahal saya belum kasih intruksi apa-apa buat lanjut hari ini.”

“Hehehe, iya biar cepet selesai dan bisa praktik lagi,” kataku sembari mengacungkan jari telunjuk dan tengah membentuk ‘peace’.

“Kita bakal banyak praktik kok. Sekarang sudah belajar sampai mana?”

Aku menunjukkan subjudul yang sedang kupelajari saat ini: “Dictionary Manipulation” pada Senja.

“Oke, pas banget. Bab ini ada praktiknya, nanti kupandu ya. Bagian string manipulation juga.”

Sembari menunggu Senja membuka laptopnya, aku kembali melanjutkan membaca:

Terakhir, untuk memanipulasi tipe data dictionary.

Tugas:
Ketikkan potongan kode berikut pada live code editor:

Fitur

Keterangan

Contoh Penggunaan

.clear()
Menghapus seluruh elemen dalam sebuah dictionary

akan menghasilkan output:

{}
.copy()

Mengembalikan copy dari setiap elemen dalam set. Serupa dengan fitur copy() pada tipe data collections lainnya, fitur copy() tidak akan mengubah nilai dari elemen asal seperti fungsi assignment.

akan menghasilkan output:

{'nik': '1211011', 'pekerjaan': 'Data Analyst', 'nama': 'Aksara'}
dan

akan menghasilkan output:

{'nik': '1211056', 'pekerjaan': 'Data Analyst', 'nama': 'Senja'}
.keys()
Mengembalikan list dari seluruh kunci akses ("key") dari setiap elemen dalam sebuah dictionary.

dapat menghasilkan output:

['nama', 'nik', 'pekerjaan']
Outputnya bersifat iterable sehingga dapat digunakan dalam perulangan.

.values()
Mengembalikan list dari seluruh nilai ("value") dari setiap elemen dalam sebuah dictionary

Variabel info_karyawan sama dengan yang diberikan pada baris fitur .keys()

dapat menghasilkan output:

['Aksara','1211011','Data Analyst']
.update()
Menambahkan kunci akses ("key") dan nilai baru ("value") ke dalam sebuah dictionary.

Variabel info_karyawan sama dengan yang diberikan pada baris fitur .keys()

dapat menghasilkan output:

{'nama': 'Aksara', 'nik': '1211011',
'pekerjaan': 'Data Analyst', 'skillset': \['Python','R'\]}

Jawaban:
\# Fitur .clear()
print(">>> Fitur .clear()")
info_karyawan = {'nama' : 'Aksara',
'nik' : '1211011',
'pekerjaan' : 'Data Analyst'}
info_karyawan.clear()
print(info_karyawan)
\# Fitur .copy()
print(">>> Fitur .copy()")
info_karyawan1 = {'nama' : 'Aksara',
'nik' : '1211011',
'pekerjaan' : 'Data Analyst'}
info_karyawan2 = info_karyawan1.copy()
info_karyawan2\['nama'] = 'Senja'
info_karyawan2\['nik'] = '1211056'
print(info_karyawan1)
print(info_karyawan2)
\# Fitur .keys()
print(">>> Fitur .keys()")
info_karyawan = {'nama' : 'Aksara',
'nik' : '1211011',
'pekerjaan' : 'Data Analyst'}
kunci_akses = list(info_karyawan.keys())
print(kunci_akses)
\# Fitur .values()
print(">>> Fitur .values()")
value_dict = list(info_karyawan.values())
print(value_dict)
\# Fitur .update()
print(">>> Fitur .update()")
info_karyawan.update({'skillset':['Python', 'R']})
print(info_karyawan)

## Useful Tips and Tricks

Untuk menentukan berapa jumlah data yang tersimpan di setiap elemen pada tuple/list, aku dapat menggunakan fungsi buit-in len().

Tugas 1:
Ketikkan potongan kode berikut pada live code editor:

akan menghasilkan output sebanyak 4. Kemudian,

akan menghasilkan output sebanyak 4.

Tugas 2:
Ternyata ada trik khusus yang dapat aku gunakan untuk mengkonversi berbagai tipe data collection. Contohnya:

Selanjutnya aku dapat melemparkan list ke dalam set() untuk mengkonversi sebuah list ke sebuah set

yang menghasilkan output:

dan melemparkan set ke dalam list() untuk mengkonversi sebuah set ke sebuah list

akan menampilkan output:

trik ini akan sangat berguna ketika aku ingin mendapatkan seluruh list element unik pada bahasa pemrograman Python.

Jawaban:
\# Tuple
print(">>> Tuple")
tuple_menu = ('Gado-gado','Ayam Goreng','Rendang','Ketoprak')
jumlah_menu = len(tuple_menu)
print(jumlah_menu)
\# List
print(">>> List")
list_menu = ['Gado-gado','Ayam Goreng','Rendang','Ketoprak']
jumlah_menu = len(list_menu)
print(jumlah_menu)
\# Konversi tipe data
print(">>> Konversi tipe data")
list_buah = ['Apel', 'Apel', 'Jeruk', 'Markisa', 'Jeruk', 'Markisa', 'Apel']
set_buah = set(list_buah)
print(set_buah)
list_buah = list(set_buah)
list_buah.sort()
print(list_buah)

## Tugas Praktek

“Aksara, untuk praktik kali ini, saya membebaskan kamu memilih case yang akan digunakan,” ujar Senja padaku.

Aku pun mulai berpikir. Selama ini aku bikin program hitung-menghitung untuk kantor dan keluarga, kok enggak bikin buat diri sendiri juga yah? Apalagi belakangan aku suka nge-boba, kayaknya memang harus dilacak deh pengeluaran dan pemasukanku minimal 9 bulan terakhir. Kalau begitu, aku pakai case pengalamanku sendiri ini saja untuk dianalisis!

Buat menganalisisnya, berarti aku harus merapikan struktur data yang kumiliki terlebih dulu dengan dictionary dan kuberi nama keuangan untuk merepresentasikan pengeluaran dan pemasukan. “Pakai format juta, lalu masukkan variabel keuangan,” ujarku sembari mengetik

Tugas:
Dari variabel keuangan, aku akan menghitung rata-rata pengeluaran dan pemasukanku selama 9 bulan terakhir. Semoga keuanganku sehat-sehat saja.

Jawaban:
\# Data keuangan
keuangan = {
'pengeluaran': [2, 2.5, 2.25, 2.5, 3.2, 2.5, 3.5, 4, 3],
'pemasukan': [7.8, 7.5, 9, 7.6, 7.2, 7.5, 7, 10, 7.5]
}
\# Perhitungan rata-rata pemasukan dan rata-rata pengeluaran
total_pengeluaran = 0
total_pemasukan = 0
for biaya in keuangan\['pengeluaran']:
total_pengeluaran += biaya
for biaya in keuangan\['pemasukan']:
total_pemasukan += biaya
rata_rata_pengeluaran = total_pengeluaran / len(keuangan\['pengeluaran'])
rata_rata_pemasukan = total_pemasukan / len(keuangan\['pemasukan'])
print(rata_rata_pengeluaran)
print(rata_rata_pemasukan)
