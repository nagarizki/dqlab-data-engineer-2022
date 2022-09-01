## Python Conditioning for Decision – Part 1

Layaknya bahasa pemrograman lainnya, bahasa pemrograman Python menyediakan statemen desisi (decision statement) untuk berinteraksi dengan variabel bertipe boolean dan operator logika. Statemen desisi dalam Python dapat dituliskan dengan menggunakan format berikut:

if conditions:
do_action_1
...
do_action_n
Dengan \<conditions> berisikan operator yang mengembalikan nilai kebenaran; ataupun beberapa operator yang mengembalikan nilai kebenaran, yang digabungkan dengan operator logika. Melalui sebuah statemen desisi (if statement), <do_action_1> sampai dengan <do_action_n> akan dijalankan saat <conditions> bernilai True.

Dalam menuliskan serangkaian aksi (<do_action_1>, ... , <do_action_n>) dalam sebuah statemen if, aku harus mengemas setiap aksi dalam sebuah blok dengan menambahkan indentasi (jorokan) dari pada aksi.

Aku tidak sabar untuk mempraktekkannya.

## Python Conditioning for Decision – Part 2

Aku mempelajari kode yang diberikan Senja dan coba mempraktekkannya ke dalam live code editor:

Ketika aku menjalankan potongan kode ini, live code editor akan menampilkan output sebagai berikut:

Kemudian, untuk melengkapi sebuah statement if, aku bisa menambahkan satu ataupun lebih statemen desisi elif, untuk melakukan pengecekan kondisi lainnya, saat kondisi dalam statement if atau elif di atasnya tidak terpenuhi.

Tugas:
Praktekkan kode berikut di live code editor pada baris setelah kode sebelumnya yang telah dibuat.

Ketika dijalankan, live code editor akan menampilkan output:

ps: Aku juga bisa mengubah nilai x sehingga lebih mudah memahami statemen desisi mana yang akan dieksekusi oleh potongan kode yang telah aku jalankan.

Jawaban:
\# Statement if

x = 4
if x % 2 == 0: # jika sisa bagi x dengan 2 sama dengan 0
print("x habis dibagi dua") # statemen aksi lebih menjorok ke dalam

\# Statement if ... elif ... else

x = 7
if x % 2 == 0: # jika sisa bagi x dengan 2 sama dengan 0
print("x habis dibagi dua")
elif x % 3 == 0: # jika sisa bagi x dengan 3 sama dengan 0
print("x habis dibagi tiga")
elif x % 5 == 0: # jika sisa bagi x dengan 5 sama dengan 0
print("x habis dibagi lima")
else:
print("x tidak habis dibagi dua, tiga ataupun lima")

## Python Conditioning for Decision – Part 3

Dari yang aku pelajari pada bagian awal dari statemen desisi, operator desisi juga dapat digunakan dengan operator logika.

Sebagai catatan tambahan, aku juga belajar bahwa aksi dalam sebuah desisi statemen dapat dituliskan desisi statemen tambahan (lainnya) yang dikenal dengan istilah nested if.

Tugas:
Praktekkan potongan kode berikut dalam live code editor.

Jawaban:
jam = 13
if jam >= 5 and jam < 12: # selama jam di antara 5 s.d. 12
print("Selamat pagi!")
elif jam >= 12 and jam < 17: # selama jam di antara 12 s.d. 17
print("Selamat siang!")
elif jam >= 17 and jam < 19: # selama jam di antara 17 s.d. 19
print("Selamat sore!")
else: # selain kondisi di atas
print("Selamat malam!")

## Tugas Praktek

Aku diminta tolong Senja untuk menghitung tagihan pembayaran karena saat ini prosesnya masih manual.

Tugas:
“Aksara, kantor kita akan merilis penawaran baru terkait jasa pembuatan data warehouse. Bisa tolong kembangkan kalkulatormu untuk menghitung tagihan pembayaran? Soalnya selama ini kita masih manual,” jelas Senja sembari memberikan contoh nota tagihan kantor.

Aku belum mengiyakan karena sedikit ragu. Mengingat sebelumnya aku sempat salah. Tapi dalam hati aku berkata, pasti bisa! Kali ini aku harus mampu membuat kalkulator lebih rumit.

Solusi yang terlintas dalam bayanganku: Kalkulator ini harus dapat menghitung subtotal setiap jasa yang diambil dari kolom harga/ hari dan total hari dari setiap jasa. Ternyata Senja juga memikirkan hal yang sama dengan instruksinya yang sangat membantu.

Tagihan untuk Mr. Yoyo

Nama Jasa

Harga per hari

Total hari

Subtotal

Data Warehousing

1000000

15

15000000

Data Cleansing

1500000

10

15000000

Data Integration

2000000

15

30000000

Data Transformation

2500000

10

25000000

Total

85000000

Jawaban:
tagihan*ke = 'Mr. Yoyo'
warehousing = { 'harga_harian': 1000000, 'total_hari':15 }
cleansing = { 'harga_harian': 1500000, 'total_hari':10 }
integration = { 'harga_harian':2000000, 'total_hari':15 }
transform = { 'harga_harian':2500000, 'total_hari':10 }
sub_warehousing = warehousing\['harga_harian'\] * warehousing\['total*hari'\]
sub_cleansing = cleansing\['harga_harian'\] * cleansing\['total*hari'\]
sub_integration = integration\['harga_harian'\] * integration\['total*hari'\]
sub_transform = transform\['harga_harian'\] * transform\['total_hari'\]
total_harga = sub_warehousing + sub_cleansing + sub_integration + sub_transform
print("Tagihan kepada:")
print(tagihan_ke)
print("Selamat pagi, anda harus membayar tagihan sebesar:")
print(total_harga)

## Tugas Praktek

Aku menunjukkan potongan kode dan hasil dari kalkulator yang telah aku buat ke Senja yang sudah berhasil menampilkan kalimat:

Selamat pagi, Anda harus membayar tagihan sebesar:

Kulihat kedua alis Senja bertaut, ini pertanda kodeku pasti ada yang keliru.
“Kalau kamu hanya memasukkan perintah ‘selamat pagi’ seakan kalau tagihan ini dikirim hanya saat pagi, padahal bisa kapan saja sesuai kebutuhan,” komentar Senja. Begini, jam pengiriman email kantor kita mulai dari 6 pagi sampai 9 malam.

Tugas:
Tolong masukkan variabel keterangan waktu tersebut di kodemu. Lalu, diatur dengan detail berikut:

Diatas jam 07 malam adalah salam 'selamat malam'
Diatas jam 05 sore adalah salam 'selamat sore'
Diatas jam 12 siang, adalah 'selamat siang'
dan selain itu 'selamat pagi'
“Oh, oke. Paham,” sahutku sembari merevisi. Saran yang bagus, kedepannya aku harus berpikir kritis.

Jawaban:
jam = 17
tagihan_ke = 'Mr. Yoyo'
warehousing = { 'harga_harian': 1000000, 'total_hari':15 }
cleansing = { 'harga_harian': 1500000, 'total_hari':10 }
integration = { 'harga_harian':2000000, 'total_hari':15 }
transform = { 'harga_harian':2500000, 'total_hari':10 }
sub_warehousing = warehousing\['harga_harian'\]*warehousing\['total_hari'\]
sub_cleansing = cleansing\['harga_harian'\]*cleansing\['total_hari'\]
sub_integration = integration\['harga_harian'\]*integration\['total_hari'\]
sub_transform = transform\['harga_harian'\]*transform\['total_hari'\]
total_harga = sub_warehousing+sub_cleansing+sub_integration+sub_transform
print("Tagihan kepada:")
print(tagihan_ke)
if jam > 19:
print("Selamat malam, anda harus membayar tagihan sebesar:")
elif jam > 17:
print("Selamat sore, anda harus membayar tagihan sebesar:")
elif jam > 12:
print("Selamat siang, anda harus membayar tagihan sebesar:")
else:
print("Selamat pagi, anda harus membayar tagihan sebesar:")
print(total_harga)

## Python Primitive Loop Control

Loop Control merupakan salah satu fitur yang mengizinkan penggunanya untuk melakukan serangkaian aksi, selama suatu kondisi yang telah ditetapkan bernilai benar. Dalam Python, terdapat dua bentuk primitif dari loop kontrol (struktur pengulangan), yaitu

while loops
for loops

## Python while loops – Part 1

Pertama-tama aku mempelajari struktur kontrol while loops menggunakan contoh berikut:

Tugas 1:
Hitung total tagihan secara manual dengan menulis potongan kode berikut ke dalam live code editor:

Setelah aku konfirmasi potongan kode yang aku buat ke Senja, aku belajar bahwa potongan kode ini tidak efektif apabila ukuran dari list tagihan bertambah. Tentunya aku akan kewalahan untuk menuliskan ekspresi penambahan pada setiap elemennya, terutama jika elemennya berjumlah banyak. Untuk mengatasi hal ini Senja memberikan masukan untuk menggunakan struktur kontrol while.

Tugas 2:
Ubah potongan kode yang telah dibuat dengan arahan Senja dan tuliskan di dalam live code editor:

Setelah dijalankan, kedua potongan kode akan mencetak output yang sama yaitu 750000.

Dari tugas di atas, aku belajar bahwa statemen while akan terus menjalankan aksi di dalamnya, selama kondisi yang dituliskan di samping kanan statemen while terus terpenuhi. Melalui penambahan nilai i sebagai salah satu aksi dalam statemen while, saat nilai i = 4, kondisi dari statemen while tidak akan terpenuhi dan eksekusi program akan dilanjutkan ke perintah print(total_tagihan).

Jawaban:
\# Tagihan
tagihan = [50000, 75000, 125000, 300000, 200000]
\# Tanpa menggunakan while loop
total_tagihan = tagihan\[0\] + tagihan\[1\] + tagihan\[2\] + tagihan\[3\] + tagihan\[4\]
print(total_tagihan)
\# Dengan menggunakan while loop
i = 0 # sebuah variabel untuk mengakses setiap elemen tagihan satu per satu
jumlah_tagihan = len(tagihan) # panjang (jumlah elemen dalam) list tagihan
total_tagihan = 0 # mula-mula, set total_tagihan ke 0
while i < jumlah_tagihan: # selama nilai i kurang dari jumlah_tagihan
total_tagihan += tagihan[i] # tambahkan tagihan[i] ke total_tagihan
i += 1 # tambahkan nilai i dengan 1 untuk memproses tagihan selanjutnya.
print(total_tagihan)

## Python while loops – Part 2

Dalam sebuah struktur kontrol pengulangan, aku dapat menggunakan perintah break untuk keluar dari struktur pengulangan dan perintah continue untuk melanjutkan proses pengulangan berikutnya.

Tugas:
Praktekkan potongan kode berikut pada live code editor.

dengan output

Jawaban:
tagihan = [50000, 75000, -150000, 125000, 300000, -50000, 200000]
i = 0
jumlah_tagihan = len(tagihan)
total_tagihan = 0
while i < jumlah_tagihan: # jika terdapat tagihan ke-i yang bernilai minus (di bawah nol), # pengulangan akan dihentikan
if tagihan\[i\] < 0:
total_tagihan = -1
print("terdapat angka minus dalam tagihan, perhitungan dihentikan!")
break
total_tagihan += tagihan\[i\]
i += 1
print(total_tagihan)

## Python while loops – Part 3

Praktekkan potongan kode berikut menggunakan live code editor.

Jika dijalankan maka akan mencetak output total tagihan sebesar 750000 (total tagihan positif).

Jawaban:
tagihan = [50000, 75000, -150000, 125000, 300000, -50000, 200000]
i = 0
jumlah_tagihan = len(tagihan)
total_tagihan = 0
while i < jumlah_tagihan: # jika terdapat tagihan ke-i yang bernilai minus (di bawah nol), # abaikan tagihan ke-i dan lanjutkan ke tagihan berikutnya
if tagihan\[i\] < 0:
i += 1
continue
total_tagihan += tagihan\[i\]
i += 1
print(total_tagihan)

## Python for loops – Part 1

Untuk perintah for loops, aku mencoba potongan kode ini menggunakan live code editor.

Jika dijalankan maka akan mencetak output total tagihan sebesar 550000 (total tagihan positif).

Jawaban:
list_tagihan = [50000, 75000, -150000, 125000, 300000, -50000, 200000]
total_tagihan = 0
for tagihan in list_tagihan: # untuk setiap tagihan dalam list_tagihan
total_tagihan += tagihan # tambahkan tagihan ke total_tagihan
print(total_tagihan)

## Python for loops – Part 2

Info: materi telah diperbarui pada tanggal 26 Desember 2021, pastikan kembali kode yang telah ditulis disesuaikan dengan default live code serta urutan materi pada bagian lesson.
Serupa dengan struktur pengulangan while, aku juga dapat memanfaatkan statement break dan continue di dalamnya. Aku mencoba potongan kode di bawah menggunakan live code editor untuk penggunaan statement break.

Jika dijalankan akan mencetak:

Untuk statement continue

Setelah dijalankan akan menghasilkan

Jawaban:
list_tagihan = [50000, 75000, -150000, 125000, 300000, -50000, 200000]

\# For loops with break
print("For loops with break")
total_tagihan_break = 0
for tagihan in list_tagihan:
if tagihan < 0:
print("Terdapat angka minus dalam tagihan, perhitungan dihentikan!")
break
total_tagihan_break += tagihan
print("Total tagihan %d." % total_tagihan_break)
print()

\# For loops with continue
print("For loops with continue")
total_tagihan_continue = 0
for tagihan in list_tagihan:
if tagihan < 0:
print("Terdapat angka minus dalam tagihan, tagihan %d dilewati!" % tagihan)
continue
total_tagihan_continue += tagihan
print("Total tagihan %d." % total_tagihan_continue)

## Python for loops – Part 3

Ternyata, aku belajar bahwa ada istilah nested loops, yaitu pengulangan bersarang. Dengan nested loops, aku dapat mengkombinasikan (menambahkan) struktur pengulangan lain di dalamnya. Aku mencoba potongan kode di bawah menggunakan live code editor:

Pada saat aku jalankan, maka output yang dihasilkan adalah:

Jawaban:
list_daerah = ['Malang', 'Palembang', 'Medan']
list_buah = ['Apel', 'Duku', 'Jeruk']
for nama_daerah in list_daerah:
for nama_buah in list_buah:
print(nama_buah+" "+nama_daerah)

## Tugas Praktek

Aku diberi informasi oleh Senja bahwa manajemen cukup puas dengan hasil kalkulator potongan harga dan pajak yang aku kembangkan. Setelahnya, aku diberikan kepercayaan lebih untuk membuat program baru.

Dalam program kali ini, aku diminta untuk menghitung total pengeluaran dan pemasukan perusahaan.

Senja pun mengingatkan akan ada penghitungan cash flow.

Melihat Senja dan tim manajemen memberikan kepercayaan yang besar kepadaku, akupun bersemangat!

Tugas:
Program yang akan aku bangun akan mengolah sebuah list yang bernama list_cash_flow. Setiap elemen dari list_cash_flow berisikan pengeluaran (bilangan negatif) dan pemasukan (bilangan positif) pada perusahaan

Dari list_cash_flow ini, aku akan menghitung total_pengeluaran dan total_pemasukan perusahaan.

Jawaban:
list_cash_flow = [
2500000, 5000000, -1000000, -2500000, 5000000, 10000000,
-5000000, 7500000, 10000000, -1500000, 25000000, -2500000
]
total_pengeluaran, total_pemasukan = 0, 0
for dana in list_cash_flow:
if dana > 0:
total_pemasukan += dana
else:
total_pengeluaran += dana
total_pengeluaran \*= -1
print(total_pengeluaran)
print(total_pemasukan)
