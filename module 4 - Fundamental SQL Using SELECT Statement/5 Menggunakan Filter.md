## Menggunakan WHERE

Klausul WHERE dari SELECT digunakan untuk memfilter data berdasarkan kondisi tertentu. Untuk syntax lengkapnya adalah sebagai berikut.

Kondisi paling sederhana memiliki format sebagai berikut

       [nama_kolom] = 'nilai_untuk_filter'

Biar lebih jelasnya, mari langsung contohkan dengan perintah berikut.

Jika dijalankan dengan baik, Live Code Editor akan menampilkan hasil berikut.

Terlihat hanya satu baris data saja yang dikeluarkan dari total sepuluh, yaitu data dimana kolom nama_produk berisi nilai 'Gantungan Kunci DQLab'.

Tugas:
Cobalah ubah perintah SELECT pada code editor untuk mengeluarkan data dengan nama_produk bernilai 'Tas Travel Organizer DQLab'. Jika semua berjalan dengan lancar, maka hasilnya akan terlihat sebagai berikut.

Jawaban:
select \* from ms_produk where nama_produk = 'Tas Travel Organizer DQLab'

## Menggunakan Operand OR

Pada subbab sebelumnya, aku telah menggunakan filter teks sederhana untuk mengeluarkan data masing-masing dengan nama_produk 'Gantungan Kunci DQLab' dan 'Tas Travel Organizer DQLab'.

Pertanyaannya, bagaimana jika ingin mengeluarkan keduanya sekaligus? Aku bisa menggunakan Operand OR.

Untuk memunculkan hasil query yang memuat data produk dengan nama_produk 'Gantungan Kunci DQLab' dan 'Tas Travel Organizer DQLab', aku dapat menggunakan logika sederhana, yaitu: Aku perlu mengambil data dengan kondisi nama_produk itu bernilai 'Gantungan Kunci DQLab' ATAU 'Tas Travel Organizer DQLab'. Logika ini bisa dinotasikan dengan menggunakan logika OR.

Sehingga, dengan menggunakan logika OR, aku dapat menggabungkan dua atau lebih kondisi untuk memfilter data. Jadi, untuk menyelesaikan problem yaitu memunculkan data dengan kondisi kolom nama_produk bernilai 'Gantungan Kunci DQLab' ATAU 'Tas Travel Organizer DQLab', dapat menggunakan syntax berikut:

Jika dijalankan dengan baik maka hasilnya akan tampak sebagai berikut.

Terlihat bukan hanya satu baris data, tapi terdapat dua baris data yang diambil karena memenuhi kondisi yang diberikan pada perintah SELECT.

Tugas:
Tambahkan nama_produk 'Flashdisk DQLab 64 GB' ke dalam tabel. Jika berjalan dengan lancar, maka hasilnya terlihat sebagai berikut.

Jawaban:
select \* from ms_produk where nama_produk = 'Gantungan Kunci DQLab' or nama_produk = 'Tas Travel Organizer DQLab' or nama_produk = 'Flashdisk DQLab 64 GB'

## Filter untuk Angka

Sebelumnya, aku telah melakukan filtering untuk teks, namun WHERE tidak terbatas untuk tipe data teks saja tapi malah umumnya untuk angka.

Berikut adalah contoh filter dimana kolom harga harus memiliki nilai di bawah 50000.

Jika dijalankan, maka aku akan mendapatkan tiga baris data sebagai berikut.

Terlihat seluruh data yang diambil memiliki kondisi harga di bawah 50000.

Tugas:
Tampilkan informasi dengan harga diatas 50000. Jika berjalan dengan lancar, maka akan mendapatkan hasil berikut.

Jawaban:
select \* from ms_produk where harga > 50000

## Menggunakan Operand AND

Jika sebelumnya aku mempelajari Operand OR, aku juga bisa menggunakan operand AND agar dua atau lebih kondisi terpenuhi semuanya. Jika salah satu kondisi tidak terpenuhi, data tidak akan diambil. Secara umum syntaxnya diilustrasikan berikut ini

Berikut adalah contoh dimana kedua kondisi digunakan dengan penghubung AND.

Jika dijalankan dengan baik, maka akan menampilkan

Tidak ada hasil yang keluar! Loh? Bingung?

Iya, karena tidak ada nama_produk yang mengandung “Gantungan Kunci DQLab” dan dengan harga di atas 50,000, sehingga tidak ada hasil yang keluar karena kedua kondisi tersebut tidak terpenuhi.

Tugas:
Cobalah ganti kondisi contoh di atas dimana harga menjadi lebih kecil dari 50000, dengan nama_produk yang sama.

Kali ini jika dijalankan maka akan memunculkan satu data sebagai berikut.

Jawaban:
select \* from ms_produk where nama_produk = 'Gantungan Kunci DQLab' and harga < 50000
