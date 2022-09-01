## Fungsi Pertama

contoh_fungsi merupakan nama dari fungsi yang aku deklarasikan dan statemen-statemen di dalamnya disebut sebagai isi (body) dari fungsi.

Tugas:
Untuk menjalankan fungsi yang telah aku deklarasikan, aku dapat menuliskan potongan kode berikut dengan mengetiknya pada live code editor pada baris berikutnya.

pemanggilan fungsi contoh_fungsi() akan menghasil output:

Jawaban:
\# Definisikan fungsi
def contoh_fungsi():
print("Halo Dunia")
print("Aku sedang belajar bahasa Python")
\# Panggil fungsi yang telah didefinisikan
contoh_fungsi()

## Fungsi Kedua

Sebuah fungsi dapat menerima serangkaian argumen pada bagian dalam kurung setelah nama fungsi telah aku definisikan.

fungsi_dengan_argumen membutuhkan dua argumen (nama_depan, nama_belakang).
Python akan menjalankan sebuah fungsi hanya ketika aku telah mensuplai jumlah argumen yang sesuai saat fungsi didefinisikan.

Tugas:
Ketik potongan kode berikut pada live code editor.

pemanggilan fungsi fungsi_dengan_argumen("John", "Doe") akan menghasilkan output:

Jawaban:
\# Definsikan fungsi
def fungsi_dengan_argumen(nama_depan, nama_belakang):
print(nama_depan + " " + nama_belakang)
\# Panggil fungsi dengan memasukkan argumen
\# nama_depan yaitu "John" dan nama_belakang "Doe"
fungsi_dengan_argumen("John", "Doe")

## Fungsi Ketiga

Saat aku melakukan pemanggilan fungsi dengan jumlah argumen yang tidak sesuai, Python akan mengembalikan pesan error yang menyatakan bahwa terdapat argumen yang belum disuplai agar fungsi dapat dijalankan dengan baik.

Berikut ini adalah contoh pesan error yang akan dikembalikan oleh Python saat aku hanya menyuplai satu argumen saja untuk fungsi_dengan_argumen:

Type Error: function fungsi_dengan_argumen() missing 1 required positional argument: nama_belakang

Bahasa Python mengizinkan aku untuk memberikan suatu nilai default terkait dengan sebuah argumen dalam sebuah fungsi. Melalui fitur ini, suatu argumen dalam sebuah fungsi akan bersifat opsional.

Tugas 1:
Aku mencoba mengetik potongan kode berikut dengan live code editor:

Argumen nama_belakang menjadi bersifat opsional saat fungsi dipanggil. Jika argumen kedua tidak disuplai Python, akan secara otomatis menset argumen nama_belakang menjadi string kosong - empty string ("").

Tugas 2:
Aku mencoba mengetik potongan kode berikut dengan live code editor:

Potongan kode berhasil dijalankan dan mengasilkan output: John

Tugas 3:
Aku mencoba mengetik potongan kode berikut dengan live code editor:

Potongan kode berhasil dijalankan dan mengasilkan output: John Doe

Jawaban:
\# Definsikan fungsi dengan nilai default argument kedua adalah "".
def fungsi_dengan_argumen(nama_depan, nama_belakang = ""):
print(nama_depan + " " + nama_belakang)
\# Panggil fungsi dengan memasukkan argumen nama_depan "John"
fungsi_dengan_argumen("John")
\# Panggil fungsi dengan memasukkan argumen
\# nama_depan yaitu "John" dan nama_belakang "Doe"
fungsi_dengan_argumen("John", "Doe")

## Tugas Praktek

Tepat ketika aku baru menyelesaikan latihan tadi, aku mendapat pesan masuk di email. Dari Senja.

Tugas:
Aksara, pekerjaan terakhirmu baru bisa saya review sore nanti. Saat ini, kita sedang butuh bantuanmu untuk menentukan nilai rata-rata untuk data yang sudah saya buatkan dalam bentuk list of numeric bertipe int/float berikut ini. Tolong kirimkan hasilnya sebelum jam 3 siang. Terima kasih.

data1 = [70, 70, 70, 100, 100, 100, 120, 120, 150, 150]
dan

data2 = [50, 60, 60, 50, 70, 70, 100, 80, 100, 90]

Aku pun melirik jam dinding kantor. Masih ada satu setengah jam sebelum deadline. Harus segera dikebut!

Aku langsung menulis kode dari data-data yang dikirimkan Senja tadi:

Jawaban:
\# Dua buah data yang tersimpan dalam tipe list
data1 = [70, 70, 70, 100, 100, 100, 120, 120, 150, 150]
data2 = [50, 60, 60, 50, 70, 70, 100, 80, 100, 90]
\# Definisikan fungsi hitng_rata_rata
def hitung_rata_rata(data):
jumlah = 0
for item in data:
jumlah += item
rata_rata = jumlah/len(data)
return rata_rata
\# Hitung nilai rata-rata dari kedua data yang dimiliki
print('Rata-rata data1:')
print(hitung_rata_rata(data1))
print('Rata-rata data2:')
print(hitung_rata_rata(data2))

## Tugas Praktek

Sudah setengah jam sejak kukirimkan hasil susunan kodeku pada Senja, ia segera membalas pesanku. Untungnya bukan revisi! Aku lebih suka dapat tambahan pekerjaan dibanding merevisi pekerjaan lama.

Tugas:
Aksara, yang kamu buat sudah cukup. Tolong buat satu fungsi untuk menghitung standar deviasi data dari data yang sudah saya berikan tadi (data dalam list of numeric bertipe int atau float).

data1 = [70, 70, 70, 100, 100, 100, 120, 120, 150, 150]
dan

data2 = [50, 60, 60, 50, 70, 70, 100, 80, 100, 90]

Baiklah, mari kuselesaikan tantangan ini. Kubuka kembali layar susunan kodeku tadi, dan mulai mengutak-atiknya. Kuingat kembali definisi matematis dari perhitungan standar deviasi, yaitu

Jawaban:
\# Dua buah data yang tersimpan dalam tipe list
data1 = [70, 70, 70, 100, 100, 100, 120, 120, 150, 150]
data2 = [50, 60, 60, 50, 70, 70, 100, 80, 100, 90]
\# Fungsi rata-rata data
def hitung_rata_rata(data):
jumlah = 0
for item in data:
jumlah += item
rata_rata = jumlah/len(data)
return rata_rata
\# Definisikan fungsi hitung_standar_deviasi
def hitung_standar_deviasi(data):
rata_rata_data = hitung_rata_rata(data)
varians = 0
for item in data:
varians += (item - rata_rata_data) ** 2
varians /= len(data)
standar_deviasi = varians ** (1/2)
return standar_deviasi
\# Hitung nilai standar deviasi dari kedua data yang dimiliki
print('Standar deviasi data1:')
print(hitung_standar_deviasi(data1))
print('Standar deviasi data2:')
print(hitung_standar_deviasi(data2))

## Tugas Praktek

“Aksara, hasil kerjamu dapat pujian di rapat tadi. Terima kasih ya sudah membantu!” ujar Senja yang menghampiri mejaku setelah keluar dari ruang rapat.

Aku mengangguk. Mungkin program tadi sederhana saja, tapi bisa bermanfaat bagi yang membutuhkannya sangat membahagiakan buatku.

“Oh ya, Aksara sebelum kamu pulang bisa tolong buatkan fungsi baru lagi? Kali ini untuk menentukan nilai-rata dan standar deviasi dari data di tabel. Nanti aku kasih data di tabelnya ya.” Senja langsung menarik bangku ke sebelahku dan membuka laptop.

Ia menunjukkan data di tabelnya seperti ini:

Luas Tanah (dalam m2)

Luas Bangunan (dalam m2)

Jarak ke Pusat Kota (dalam km)

Harga (dalam ratus juta)

70

50

15

500

70

60

30

400

70

60

55

300

100

50

30

700

100

70

25

1000

100

70

50

650

120

100

20

2000

120

80

50

1200

150

100

50

1800

150

90

15

3000

Tugas:
Dari data ini, berarti aku harus menjalankan fungsi baru dengan nama variabel deksripsi_properti. Aku pun mengangkat jempol pada Senja seakan bilang, "Serahkan padaku!"

Setelah kupelajari kembali, data ini sebenarnya telah direpresentasikan ke dalam dict dengan nama tabel_properti. Kalau begitu, aku bisa mulai kodeku seperti berikut ini.

Jawaban:
\# Data properti
tabel_properti = {
'luas_tanah': [70, 70, 70, 100, 100, 100, 120, 120, 150, 150],
'luas_bangunan': [50, 60, 60, 50, 70, 70, 100, 80, 100, 90],
'jarak': [15, 30, 55, 30, 25, 50, 20, 50, 50, 15],
'harga': [500, 400, 300, 700, 1000, 650, 2000, 1200, 1800, 3000]
}
\# Fungsi rata-rata data
def hitung_rata_rata(data):
jumlah = 0
for item in data:
jumlah += item
rata_rata = jumlah/len(data)
return rata_rata
\# Fungsi hitung_standar_deviasi
def hitung_standar_deviasi(data):
rata_rata_data = hitung_rata_rata(data)
varians = 0
for item in data:
varians += (item - rata_rata_data) ** 2
varians /= len(data)
standar_deviasi = varians ** (1/2)
return standar_deviasi
\# Definisikan fungsi untuk menghitung rata-rata dan standar deviasi
\# setiap kolom pada tabel_properti yang diberikan oleh key dict.
def deskripsi_properti(tabel):
for key in tabel.keys():
print('Rata-rata ' + key + ':')
print(hitung_rata_rata(tabel[key]))
print('Standar deviasi ' + key + ':')
print(hitung_standar_deviasi(tabel[key]))
print('')
\# Panggil fungsi deskripsi_properti untuk menghitung rata-rata
\# dan standar deviasi setiap kolom pada tabel_properti
deskripsi_properti(tabel_properti)
