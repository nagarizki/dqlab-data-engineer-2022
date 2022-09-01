## Apa itu String Manipulation?

Aku belajar bahwa String Manipulation adalah teknik yang digunakan dalam memanipulasi data yang disimpan dalam tipe data str. Pada bahasa Python, untuk mempermudah proses pengolahan data, tipe data string dapat diperlakukan layaknya seperti tipe data list.

Tugas:
Aku mengikuti contoh yang diberikan dengan mengetik syntax pada live code editor untuk memahami bagaimana String Manipulation bekerja pada Python.

akan menghasilkan output: SePatu NiKo

akan menghasilkan output: SePatu

akan menghasilkan output: NiKo

akan menghasilkan output: 11

Catatan: fungsi built-in len() juga dapat digunakan untuk menentukan jumlah karakter pada variabel bertipe string yang dimiliki.

Jawaban:
nama_produk = "Sepatu Niko"
nama_produk = nama_produk\[:2] + "P" + nama_produk\[3:9] + "K" + nama_produk\[-1]
print(nama_produk)
print(nama_produk\[:7])
print(nama_produk\[7:])
print(len(nama_produk))

## Operator “+” untuk Tipe Data String

Setelah aku mempelajari String Manipulation, sekarang aku beralih ke Operator +. Operator + pada dua string akan secara otomatis menggabungkan kedua string tersebut. Operator + juga dapat digunakan untuk menambahkan beberapa string secara bersamaan.

Aku mengikuti contoh yang diberikan dengan mengetik syntax pada live code editor untuk memahami bagaimana Operation + bekerja pada Python.

Tugas 1:

akan menghasilkan output: John Doee

Tugas 2:

Selanjutnya aku mencoba mengetik kode berikut di live code editor pada baris berikutnya

akan menghasilkan output: Hi, saya John Doee umur 27 tahun, tinggal di Jl. Anggrek No. 100.

Jawaban:
nama_depan = 'John'
nama_belakang = 'Doee'
nama_lengkap = nama_depan + ' ' + nama_belakang
print(nama_lengkap)
umur = '27 tahun'
alamat = 'Jl. Anggrek No. 100'
nama_umur_alamat = 'Hi, saya ' + nama_lengkap + ' umur ' + umur + ', tinggal di ' + alamat + '.'
print(nama_umur_alamat)

## Menghilangkan Spasi di Awal dan/atau di Akhir

Sekarang aku akan mempelajari bagaimana menghilangkan kelebihan spasi yang dimiliki di awal dan/atau di akhir variabel string. Pertama, aku melihat fitur yang diberikan pada tabel contoh.

Tugas:
Agar lebih memahami bagaimana penerapan fitur ini pada Python, aku akan mengikuti contoh yang tercantum pada tabel dengan cara mengetikkannya pada live code editor.

Fitur

Keterangan

Contoh Penggunaan

.strip()
Menghilangkan kelebihan spasi pada awal dan akhir string.

akan menghasilkan output:

'halo, selamat siang!'

.lstrip()

Menghilangkan kelebihan spasi pada awal string.

akan menghasilkan output:

'halo, selamat siang! '

.rstrip()

Menghilangkan kelebihan spasi pada akhir string.

akan menghasilkan output:

' halo, selamat siang!'

Jawaban:
/# Fitur .strip()
print(">>> Fitur .strip()")
kata_sambutan = ' halo, selamat siang! '
kata_sambutan = kata_sambutan.strip()
print(kata_sambutan)
/# Fitur .lstrip()
print(">>> Fitur .lstrip()")
kata_sambutan = ' halo, selamat siang! '
kata_sambutan = kata_sambutan.lstrip()
print(kata_sambutan)
/# Fitur .rstrip()
print(">>> Fitur .rstrip()")
kata_sambutan = ' halo, selamat siang! '
kata_sambutan = kata_sambutan.rstrip()
print(kata_sambutan)

## Merubah Caps pada String

Pada bagian ini, aku akan mempelajari cara merubah caps (penggunaan huruf besar dan kecil). Jika diawal kalimat pada suatu string yang dimiliki belum berupa huruf kapital, maka dengan menggunakan fitur .capitalize() kita dengan mudah mengubah string tersebut menjadi kalimat yang benar secara bahasa.

Tugas:
Aku mengikuti contoh yang diberikan dengan mengetik syntax pada live code editor untuk memahami bagaimana fitur .capitalize(), .lower(), dan .upper() bekerja pada Python.

Fitur

Keterangan

Contoh Penggunaan

.capitalize()

Mengubah elemen pertama dari string menjadi huruf kapital.

akan menghasilkan output:

Belajar bahasa python

.lower()

Mengubah seluruh huruf dalam teks (string) menjadi huruf kecil

akan menghasilkan output:

belajar bahasa python.

.upper()

Mengubah seluruh huruf dalam teks (string) menjadi huruf besar

akan menghasilkan output:

BELAJAR BAHASA PYTHON.

Jawaban:
\# Fitur .capitalize()
print(">>> Fitur .capitalize()")
judul_buku = 'belajar bahasa Python'
print(judul_buku.capitalize())
\# Fitur .lower()
print(">>> Fitur .lower()")
judul_buku = 'Belajar Bahasa PYTHON.'
print(judul_buku.lower())
\# Fitur .upper()
print(">>> Fitur .upper()")
judul_buku = 'Belajar Bahasa PYTHON.'
print(judul_buku.upper())

## Pemecahan, Penggabungan, dan Penggantian String

Info: materi telah diperbarui pada tanggal 8 Desember 2021, pastikan kembali kode yang telah ditulis disesuaikan dengan bagian Lesson.
Pada bagian ini, aku akan mempelajari bagaimana cara memecah suatu string dengan kondisi tertentu sehingga menghasilkan list of string. Kemudian, akan dipelajari bagaimana cara menggabungkan beberapa list of string menjadi string saja. Akhirnya, aku akan mengganti sub-string tertentu dengan sub-string lainnya sehingga mengubah string awalnya.

Tugas:
Agar lebih memahami bagaimana penerapannya pada Python, aku akan mengikuti contoh penggunaan yang diberikan dari tabel berikut dengan mengetik syntax pada live code editor.

Fitur

Keterangan

Contoh Penggunaan

.split()

Memecah sebuah string berdasarkan string lainnya ke dalam sebuah list.

memecah string berdasarkan kata dan

akan menghasilkan output:

['ani', 'budi', 'wati', 'johan']

memecah string berdasarkan spasi " "

akan menghasilkan output:

['ani', 'dan', 'budi', 'dan', 'wati', 'dan', 'johan']

.join()

Menggabungkan sebuah list yang berisikan string berdasarkan sebuah string yang telah didefinisikan.

akan menghasilkan output:

'Ricky dan Peter dan Jordan'

dan

akan menghasilkan output:

'Ricky Peter Jordan'

.replace()

Menggantikan kemunculan suatu string tertentu dengan string lainnya dalam sebuah string.

akan menghasilkan output:

'jeruk malang jeruk yang paling segar, jeruk sehat, jeruk nikmat'

Jawaban:
\# Fitur .split()
print(">>> Fitur .split()")
frasa = "ani dan budi dan wati dan johan"
karakter = frasa.split("dan")
print(karakter)
kata = frasa.split(" ")
print(kata)
\# Fitur .join()
print(">>> Fitur .join()")
pemisah = " dan "
karakter = ["Ricky", "Peter", "Jordan"]
frasa = pemisah.join(karakter)
print(frasa)
frasa = " ".join(karakter)
print(frasa)
\# Fitur .replace()
print(">>> Fitur .replace()")
frasa = "apel malang apel yang paling segar, apel sehat, apel nikmat"
frasa = frasa.replace("apel", "jeruk")
print(frasa)

## Menentukan Posisi dan Jumlah Sub-string pada String

Pada bagian ini, aku akan mempelajari bagaimana cara menentukan posisi awal suatu sub-string dan jumlah kemunculan sub-string tersebut pada suatu string agar lebih memahami bagaimana penerapannya pada Python.

Tugas:
Aku akan mengikuti contoh penggunaan yang diberikan dari tabel berikut dengan mengetiknya pada live code editor.

Fitur

Keterangan

Contoh Penggunaan

.find()

Mengembalikan posisi dari sebuah teks (sub-string) lainnya dalam sebuah string.

akan menghasilkan output: 0

dikarenakan kalimat diawali dengan kata Apel

akan menghasilkan output: 5

kata malang muncul dimulai dari indeks ke-5 ketika setiap karakter dalam string direpresentasikan sebagai array.

.count()

Menghitung jumlah kemunculan sebuah teks (string) lainnya dalam suatu string (string yang dicari bersifat case sensitive).

akan menghasilkan output: 3

Hal ini dikarenakan kata Apel di awal kalimat tidak sama dengan apel (Apel diawali huruf kapital dan kata yang dicari diawali huruf kecil)

Jawaban:
teks = "Apel malang adalah apel termanis dibanding apel-apel lainnya"
\# Fitur .find()
print(">>> Fitur .find()")
print(teks.find("Apel"))
print(teks.find("malang"))
\# Fitur .count()
print(">>> Fitur .count()")
kemunculan_kata_apel = teks.count("apel")
print(kemunculan_kata_apel)

## Menentukan String Apakah Diawali/Diakhiri oleh Sub-string

Pada bagian ini, aku akan mempelajari bagaimana menentukan apakah suatu string diawali atau diakhiri dengan suatu substring (teks) tertentu.

Tugas:
Agar lebih memahami bagaimana penerapannya pada Python, aku akan mengikuti contoh penggunaan yang diberikan menggunakan fitur dalam tabel berikut dengan mengetiknya pada live code editor.

Fitur

Keterangan

Contoh Penggunaan

.startswith()
Mengembalikan nilai kebenaran True ketika sebuah teks (string) diawali dengan sebuah teks lainnya.

akan menghasilkan output: True

dan

akan menghasilkan output: False

.endswith()

Mengembalikan nilai kebenaran True ketika sebuah teks (string) diakhiri dengan sebuah teks lainnya.

Variabel teks sama dengan yang digunakan dalam baris fitur .startswith()

akan menghasilkan output: True

dan

akan menghasilkan output: False

Jawaban:
\# Fitur .startswith()
print(">>> Fitur .startswith()")
teks = "Apel malang adalah apel termanis dibanding apel-apel lainnya"
print(teks.startswith("Apel"))
print(teks.startswith("apel"))
\# Fitur .endswith()
print(">>> Fitur .endswith()")
print(teks.endswith("lainnya"))
print(teks.endswith("apel"))

## Tugas Praktek

Aku mengecek ponsel. Sejak kukirimkan progress latihanku terakhir pada Senja, belum ada kabar lagi sampai saat ini. Senja memang tiba-tiba pergi dari mejanya tadi. Sedikit bosan, aku coba membuka-buka dokumen di laptop. Aku menemukan folder “LATIHAN” dan teringat kalau ada satu latihan kecil yang belum kukerjakan. “Mumpung lagi lowong, aku coba deh.”

Aku mengeklik dokumen PENGOLAHAN DATA TEKS. Di dalamnya aku diminta untuk meneliti popularitas antara buah salak dan buah jeruk berdasarkan judul artikel yang muncul di majalah Buah Sehat. Aku mulai menyiapkan susunan kodeku:

judul_artikel = [
"Buah Salak Baik untuk Mata", "Buah Salak Kaya Potasium",
"Buah Jeruk Kaya Vitamin C", "Buah Salak Kaya Manfaat",
"Salak Baik untuk Jantung", "Jeruk dapat Memperkuat Tulang",
"Jeruk Mencegah Penyakit Asma", "Jeruk Memperkuat Gigi",
"Jeruk Mencegah Kolesterol Jahat", "Salak Mencegah Diabetes",
"Salak Memperkuat Dinding Usus", "Salak Baik untuk Darah",
"Jeruk Kaya Manfaat untuk Jantung", "Salak si Kecil yang Baik",
"Jeruk dan Salak Buah Kaya Manfaat", "Buah Jeruk Enak",
"Tips Panen Jeruk Ribuan Kilo", "Tips Bertanam Salak",
"Salak Manis untuk Berbuka", "Jeruk Baik untuk Wajah"
]

Tugas:
“Kalau mengikuti yang sudah kupelajari, langkah pertama adalah menghitung jumlah kemunculan kata jeruk dan salak di tiap judul artikel,” batinku.

Aku kembali berkutat di depan layar laptop.

Jawaban:
judul_artikel = [
"Buah Salak Baik untuk Mata", "Buah Salak Kaya Potasium",
"Buah Jeruk Kaya Vitamin C", "Buah Salak Kaya Manfaat",
"Salak Baik untuk Jantung", "Jeruk dapat Memperkuat Tulang",
"Jeruk Mencegah Penyakit Asma", "Jeruk Memperkuat Gigi",
"Jeruk Mencegah Kolesterol Jahat", "Salak Mencegah Diabetes",
"Salak Memperkuat Dinding Usus", "Salak Baik untuk Darah",
"Jeruk Kaya Manfaat untuk Jantung", "Salak si Kecil yang Baik",
"Jeruk dan Salak Buah Kaya Manfaat", "Buah Jeruk Enak",
"Tips Panen Jeruk Ribuan Kilo", "Tips Bertanam Salak",
"Salak Manis untuk Berbuka", "Jeruk Baik untuk Wajah"
]
jumlah_artikel_jeruk = 0 #judul_artikel.count("Jeruk")
jumlah_artikel_salak = 0 #judul_artikel.count("Salak")
for judul in judul_artikel:
if judul.count("Jeruk") > 0:
jumlah_artikel_jeruk += 1
if judul.count("Salak") > 0:
jumlah_artikel_salak += 1
print(jumlah_artikel_jeruk)
print(jumlah_artikel_salak)

## Tugas Praktek

Setelah selesai menghitung jumlah kemunculan kata, aku mencoba berpikir dari sudut pandang si pemilik majalah. Kalau aku jadi mereka, tentunya aku juga ingin tahu apakah kata yang muncul itu bermuatan positif atau tidak. Nah ini!

Tugas:
Dengan cepat, aku mendeklarasikan daftar bernama kata_positif yang berisi nuansa kata positif untuk menghitung jumlah kemunculan kata_positif bagi tiap artikel jeruk dan salak, seperti ini:

Jawaban:
judul_artikel = [
"Buah Salak Baik untuk Mata", "Buah Salak Kaya Potasium",
"Buah Jeruk Kaya Vitamin C", "Buah Salak Kaya Manfaat",
"Salak Baik untuk Jantung", "Jeruk dapat Memperkuat Tulang",
"Jeruk Mencegah Penyakit Asma", "Jeruk Memperkuat Gigi",
"Jeruk Mencegah Kolesterol Jahat", "Salak Mencegah Diabetes",
"Salak Memperkuat Dinding Usus", "Salak Baik untuk Darah",
"Jeruk Kaya Manfaat untuk Jantung", "Salak si Kecil yang Baik",
"Jeruk dan Salak Buah Kaya Manfaat", "Buah Jeruk Enak",
"Tips Panen Jeruk Ribuan Kilo", "Tips Bertanam Salak",
"Salak Manis untuk Berbuka", "Jeruk Baik untuk Wajah"
]
kata_positif = ["Kaya", "Baik", "Mencegah", "Memperkuat"]
kata_positif_jeruk = 0
kata_positif_salak = 0
for judul in judul_artikel:
for kata in kata_positif:
if judul.count("Jeruk") > 0 and judul.count(kata) > 0:
kata_positif_jeruk += 1
if judul.count("Salak") > 0 and judul.count(kata) > 0:
kata_positif_salak += 1
print(kata_positif_jeruk)
print(kata_positif_salak)
