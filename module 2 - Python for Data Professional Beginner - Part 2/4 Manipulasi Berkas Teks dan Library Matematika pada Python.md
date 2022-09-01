## Membaca Berkas Teks – Part 1

Info: materi telah diperbarui pada tanggal 15 Oktober 2021. Pastikan kembali kode yang telah ditulis disesuaikan dengan tugas terbaru.

Setelah mempelajari bagaimana membuka/membuat sebuah berkas teks dalam Python, aku akan mempelajari sintaks untuk dapat membaca isi dari sebuah berkas. Untuk membaca isi dari sebuah teks aku dapat menggunakan potongan kode berikut.

Aku akan mengasumsikan baris-baris di bawah comment merupakan isi dari “hello.txt”.

Kita sedang belajar Python
Tepatnya belajar memanipulasi berkas teks
Memanipulasi berkas dengan Python sangatlah mudah!
Note: Karena ada perubahan hosting file hello.txt yang tidak ditempatkan di direktori lokal sistem DQLab kamu dapat mempraktikkan bagian A1 dan A2 pada komputer kamu. Untuk itu file hello.txt dapat kamu unduh melalui https://storage.googleapis.com/dqlab-dataset/hello.txt.

A1. Membaca file hello.txt dengan fungsi read() dan menutup file

Perintah ini aku gunakan untuk menutup berkas setelah selesai digunakan

Akan menghasilkan output:

Kita sedang belajar Python
Tepatnya belajar memanipulasi berkas teks
Memanipulasi berkas dengan Python sangatlah mudah!
Selain dapat membaca dan menampung isi dari sebuah berkas secara sekaligus menggunakan fungsi read(), aku juga dapat menggunakan fungsi readline() ataupun readlines() untuk membaca isi dari suatu berkas teks. Dengan menggunakan fungsi readline(), Python akan membaca konten dari sebuah berkas secara baris per baris, dimulai dari baris paling awal.

A2. Membaca file hello.txt dengan fungsi readline()

dengan menggunakan fungsi readline() dapat aku gunakan untuk membaca isi dari file secara tersedia dalam berkas “hello.txt” baris per baris

perintah ini aku gunakan untuk menutup berkas setelah selesai digunakan

akan menghasilkan output:

Kita sedang belajar Python
Tepatnya belajar memanipulasi berkas teks

Tugas Praktik:
Well, aku sudah mempraktikkan membaca berkas teks secara lokal di komputer ku. Sekarang aku akan mencoba membaca berkas teks yang sama yang berada di url https://storage.googleapis.com/dqlab-dataset/hello.txt. Di code editor akupun mengetikkan perintah berikut

Aku akan mengecek apakah permintaan yang dilakukan melalui url dapat dipenuhi. Selanjutnya aku mengetikkan kode berikut

yang kemudian aku dapati hasil berikut di console

Ini apa ya? Akupun mencarinya melalui mesin pencari google dan melalui tautan https://en.wikipedia.org/wiki/List_of_HTTP_status_codes saya dapatkan informasi bahwa kode status HTTP 200 adalah response OK dari url di mana file hello.txt disimpan.

Untuk mencetak isi berkas hello.txt yang telah dibaca dapat aku lakukan melalui potongan kode yang ditunjukkan berikut ini

Ketika aku jalankan maka aku memperoleh hasil di console seperti berikut ini

Sayangnya setelah aku amati terlihat bahwa hasilnya tidak sama dengan isi berkas hello.txt.

Jawaban:
import requests
url = "https://storage.googleapis.com/dqlab-dataset/hello.txt"
response = requests.get(url)

\# Cetak kode status dari response

print(response)

\# Cetak isi file hello.txt menggunakan method response.iter_lines()

print("\n>> Cetak isi file hello.txt menggunakan method response.iter_lines():")
for baris in response.iter_lines():
print(baris)

## Membaca Berkas Teks – Part 2

Info: materi telah diperbarui pada tanggal 15 Oktober 2021. Pastikan kembali kode yang telah ditulis disesuaikan dengan tugas terbaru.
Fungsi readlines() akan mengembalikan sebuah list yang setiap elemennya merupakan setiap baris dalam sebuah berkas teks.

Note: Karena ada perubahan hosting file hello.txt yang tidak ditempatkan di direktori lokal sistem DQLab kamu dapat mempraktikkan bagian A1 dan A2 pada komputer kamu. Untuk itu file hello.txt dapat kamu unduh melalui https://storage.googleapis.com/dqlab-dataset/hello.txt.

A1. Membaca file hello.txt dengan fungsi readlines()
Aku membuka kembali file “hello.txt”

Dan membaca dengan fungsi readlines(),

Syntax ini akan menghasilkan output:

[“Kita sedang belajar Python”, “Tepatnya belajar memanipulasi berkas teks”,
“Memanipulasi berkas dengan Python sangatlah mudah!”]

A2. Membaca file hello.txt dengan menerapkan looping
Selain menggunakan fungsi-fungsi standar yang telah disediakan oleh Python, aku juga dapat membaca isi dari sebuah file secara baris per baris dengan menggunakan for loops. Simaklah contoh berikut ini dengan tetap membaca file dari “hello.txt”

untuk setiap baris sebagai variabel line dalam berkas dengan nama variabel file

Akan menghasilkan output:

Kita sedang belajar Python
Tepatnya belajar memanipulasi berkas teks
Memanipulasi berkas dengan Python sangatlah mudah!

Tugas Praktik:
Aku menjadi penasaran dengan hasil yang telah aku dapatkan sebelumnya. Apakah ada method/attribut lain gak ya untuk mencetak isi dari berkas hello.txt di https://storage.googleapis.com/dqlab-dataset/hello.txt.

Akupun mencoba mengunakan atribut .text dari variabel response, seperti yang ditampilkan pada baris kedelapan.

Hasil dari perintah ini di console adalah

Waaw.... Penggunaan atribut .text menghasilkan isi berkas hello.txt sesuai dengan isi yang seharusnya.

Tips: Trik ini efektif digunakan ketika mengambil data melalui web scrapping.

Jawaban:
import requests
url = "https://storage.googleapis.com/dqlab-dataset/hello.txt"
response = requests.get(url)
\# Cetak kode status dari response
print(response)
\# Cetak isi file hello.txt menggunakan atribut response.text
print("\n>> Cetak isi file hello.txt menggunakan atribut response.text:")
print(response.text)

## Menulis Berkas Teks – Part 1

Untuk menuliskan isi dari suatu berkas, aku dapat menggunakan fungsi write() atau writelines() yang telah disediakan oleh Python. Sebelum masuk ke dalam contoh penggunaan fungsi write() atau writelines(), penting bagiku untuk mengingat bahwa mode yang aku spesifikasikan pada fungsi open() akan mempengaruhi bagaimana Python menuliskan isi ke dalam berkas teks. Jika aku menggunakan mode w, maka Python akan menghapus seluruh isi dalam berkas sebelum menuliskan konten yang aku spesifikasikan.

Asumsikan baris-baris di bawah comment ini merupakan isi dari “hello.txt”

Kita sedang belajar Python
Tepatnya belajar memanipulasi berkas teks
Memanipulasi berkas dengan Python sangatlah mudah!

Tugas:
Perintah ini aku gunakan untuk membuka/membuat sebuah berkas teks

Untuk setiap baris sebagai variabel line dalam berkas dengan nama variabel file

Seusai program selesai dijalankan, baris-baris di bawah comment ini merupakan isi dari "hello.txt"

Sekarang kita belajar menulis dengan menggunakan Python
Menulis konten file dengan mode w (write).

Jawaban:
\# Menulis ke file hello.txt
file = open("hello.txt", "w")
file.write("Sekarang kita belajar menulis dengan menggunakan Python")
file.write("Menulis konten file dengan mode w (write).")
file.close()

## Menulis Berkas Teks – Part 2

Ketika aku menulis pada berkas teks menggunakan mode a, Python tidak akan menghapus isi dalam berkas dan hanya akan menambahkan konten. Aku mempelajari contoh berikut untuk memahami penggunaan fungsi write() dan writelines()

Tugas:
Pertama, aku mengasumsikan baris-baris di bawah comment ini merupakan isi dari “hello.txt”

Kita sedang belajar Python
Tepatnya belajar memanipulasi berkas teks
Memanipulasi berkas dengan Python sangatlah mudah!
Perintah ini aku gunakan untuk membuka/membuat sebuah berkas teks dengan menggunakan mode “a”, untuk menambahkan beberapa baris pada berkas teks setelah isi dari berkas awalnya

Aku menggunakan fungsi readlines

Jawaban:
\# Menulis ke file dengan mode append
file = open("hello.txt", "a")
file.writelines([
"Sekarang kita belajar menulis dengan menggunakan Python",
"Menulis konten file dengan mode a (append)."
])
file.close()

## Fungsi dalam Library Matematika – Part 1

Di dalam library math aku mempelajari berbagai fungsi, beberapa diantaranya dapat dilihat pada tabel di bawah ini.

Tugas:
Aku mengetikkan potongan kode berikut dalam live code editor:

Fitur

Keterangan

Contoh Penggunaan

math.ceil()
Menerima input berupa bilangan dan mengembalikan pembulatan ke atas untuk bilangan input.

akan menghasilkan output: 11

akan menghasilkan output: 14

math.floor()

Menerima input berupa bilangan dan mengembalikan hasil pembulatan ke bawah untuk bilangan input.

akan menghasilkan output: 10

akan menghasilkan output: 13

math.fabs()

Menerima input berupa bilangan dan mengembalikan hasil absolut dari bilangan input.

akan menghasilkan output: 10.32

akan menghasilkan output: 13.87

math.factorial()

Menerima input berupa bilangan dan mengembalikan hasil faktorial dari bilangan input

faktorial dari 5 adalah 5 _ 4 _ 3 _ 2 _ 1

akan menghasilkan output: 120

math.fsum()

Menerima input berupa tipe data collection (tuple, list, etc.) dan mengembalikan hasil penjumlahan setiap elemennya.

akan menghasilkan output: 6

Jawaban:
\# Import library math
import math
\# Fungsi math.ceil()
print(">>> Fungsi math.ceil()")
x = 10.32
y = 13.87
x_ceil = math.ceil(x)
y_ceil = math.ceil(y)
print(x_ceil)
print(y_ceil)
\# Fungsi math.floor()
print(">>> Fungsi math.floor()")
x_floor = math.floor(x)
y_floor = math.floor(y)
print(x_floor)
print(y_floor)
\# Fungsi math.fabs()
print(">>> Fungsi math.fabs()")
x = 10.32
y = -13.87
x = math.fabs(x)
y = math.fabs(y)
print(x)
print(y)
\# Fungsi math.factorial()
print(">>> Fungsi math.factorial()")
x_factorial = math.factorial(5)
print(x_factorial)
\# Fungsi math.fsum()
print(">>> Fungsi math.fsum()")
x = [1, 2, 3, 4, 5, 6, -6, -5, -4]
total = math.fsum(x)
print(total)

## Fungsi dalam Library Matematika – Part 2

Aku masih melanjutkan bagian terakhir dari (bulit-in) library matematika pada Python yang dapat digunakan untuk perhitungan matematis.

Tugas:
Aku mempraktekkan potongan kode berikut dalam live code editor:

Fitur

Keterangan

Contoh Penggunaan

math.log()
Menerima input berupa dua buah bilangan (asumsikan x dan y) dan mengembalikan sebuah bilangan (z) di mana z merupakan hasil log basis y dari x (atau dengan kata lain x merupakan hasil pemangkatan dari z terhadap y)

akan menghasilkan output 3

akan menghasilkan output 4

akan menghasilkan output 4

math.sqrt()
Menerima input berupa sebuah bilangan dan mengembalikan hasil akar pangkat dua (akar kuadrat) dari bilangan tersebut

akan menghasilkan output: 10

akan menghasilkan output: 1.4142135.

math.copysign()
Menerima input berupa dua buah bilangan dan mengembalikan bilangan pertama sesuai dengan tanda yang dimiliki oleh bilangan kedua

akan menghasilkan output: -10.32

akan menghasilkan output: -13.87

akan menghasilkan output: 15

Jawaban:
\# Import library math
import math
\# Fungsi math.log()
print(">>> Fungsi math.log()")
\# x = log basis 2 dari 8
x = math.log(8, 2)
\# y = log basis 3 dari 81
y = math.log(81, 3)
\# z = log basis 10 dari 10000
z = math.log(10000, 10)
print(x)
print(y)
print(z)
\# Fungsi math.sqrt()
print(">>> Fungsi math.sqrt()")
\# akar kuadrat dari 100
x = math.sqrt(100)
print(x)
\# akar kuadrat dari 2
y = math.sqrt(2)
print(y)
\# Fungsi math.copysign()
print(">>> Fungsi math.copysign()")
x = 10.32
y = -13.87
z = -15
x = math.copysign(x, z)
y = math.copysign(y, z)
z = math.copysign(z, 10)
print(x)
print(y)
print(z)
