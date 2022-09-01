## Mengambil Seluruh Kolom dalam suatu Tabel

“Jadi, bagaimana cara mengakses data dari database, Nja? Soalnya sejauh aku mencoba, aku sudah dapat hak akses tapi tidak paham cara membuka maupun mengakses tabel dan data dari database.”

Aku akhirnya menyampaikan kendalaku pada Senja.

“Untuk mengakses data di database, kita dapat menggunakan SELECT statement. Pada SELECT statement kita menyatakan kolom - kolom mana saja yang ingin kita tampilkan dari suatu tabel di database. SELECT statement tidak berdiri sendiri. Setelah menyatakan kolom - kolom yang ingin ditampilkan, kita melanjutkan dengan FROM. Di FROM inilah kita menyatakan dari tabel mana data yang ingin kita tampilkan berada. SELECT… FROM… adalah statement paling sederhana di SQL, dan merupakan bagian utama dari query. Kita tidak bisa meng-query data tanpa menggunakan statement ini,” jelas Senja.

Senja juga menunjukkan padaku Query dasar dan sederhana perintah SELECT yang berfungsi untuk menampilkan seluruh kolom, sebagai berikut:

Kata awal, yaitu SELECT digunakan untuk menginformasikan kepada sistem bahwa kita ingin mengambil data.
Tanda \* (bintang) artinya seluruh kolom perlu diambil dari tabel yang dirujuk. Tanda ini sering juga disebut sebagai wildcard.
FROM [NAMA_TABLE], artinya table yang akan diambil datanya.
Tanda ; (titik koma) adalah tanda yang menyatakan akhir dari perintah SELECT atau SQL lain.

Senja mengajak aku untuk langsung mempraktekkan perintah SQL SELECT untuk menampilkan data pada tabel yang bernama ms_produk.

Jika aku menjalankan tombol RUN, maka aku akan mendapatkan tabel seperti berikut:

Jawaban:
select \* from ms_produk

## Mengambil Satu Kolom dari Tabel

Aku sudah cukup paham dengan penjelasan Senja tadi. Tapi, masih ada satu yang mengganjal. “Bagaimana kalau aku hanya ingin menampilkan satu kolom saja dari suatu tabel/data, Nja?”

“Secara umum penggunaan perintah SELECT untuk mengambil satu kolom dinyatakan oleh sintaks berikut ini,” ujar Senja sambil menggeser layar laptopnya agar bisa kuperhatikan:

“Kita coba ya dengan menampilkan data pelanggan yang ada di database. Kita sudah menggunakan perintah SELECT sebelumnya untuk mengambil seluruh kolom. Nah, berikut adalah contoh query untuk mengambil satu kolom saja yaitu nama_produk,” tambah Senja.

Aku mencatat beberapa tampilan penting yang menjadi contoh dari Senja buatku.

Ketikkan perintah berikut pada code editor dan kemudian klik tombol Run,

Hasilnya, sistem database akan menampilkan data nama_produk saja dari tabel ms_produk seperti terlihat sebagai berikut.

Terlihat ada sepuluh nama peralatan kantor yang ditampilkan, dan jumlah ini sesuai dengan jumlah seluruh row yang terdapat pada tabel ms_produk.

Jawaban:
select nama_produk from ms_produk

## Mengambil Lebih dari Satu Kolom dari Tabel

Tabel ms_produk memiliki lebih dari satu kolom data. Kalau aku ingin mengambil kolom lainnya, aku hanya perlu menuliskan tiap kolom yang ingin ditampilkan dipisahkan dengan tanda koma, seperti contoh berikut untuk dua kolom.

Menggunakan tabel ms_produk, aku menggunakan perintah SELECT berikut untuk menampilkan dua kolom, kode_produk dan nama_produk.

Hasilnya, sistem database akan menampilkan data kode_produk, nama_produk dari tabel ms_produk seperti terlihat sebagai berikut.

Terlihat data dengan dua kolom ditampilkan yaitu kode_produk dan nama_produk. Jumlah data yang dikeluarkan masih sepuluh, sesuai dengan jumlah seluruh row yang terdapat pada tabel ms_produk.

Tugas:
Sekarang gantilah perintah SELECT di code editor untuk menampilkan nama_produk dan harga dari tabel yang sama. Ingat untuk memisahkan setiap kolom dengan comma (,).

Jika berjalan dengan lancar, maka hasilnya akan terlihat sebagai berikut.

Jawaban:
select nama_produk, harga from ms_produk

## Membatasi Pengambilan Jumlah Row Data

Selain pembatasan kolom, aku bisa membatasi jumlah baris data yang diambil. Seperti yang aku pelajari di materi RDMS sebelumnya, bahwa untuk tiap produk RDBMS, caranya agak berbeda-beda. Untuk MySQL dan PostgreSQL, aku dapat menggunakan LIMIT. Secara umum syntaxnya dinyatakan sebagai berikut

Sebagai contoh, aku bisa menggunakan perintah LIMIT untuk membatasi pengambilan data dari tabel ms_produk sebanyak tiga baris data (row).

Jika berjalan dengan lancar, akan terlihat hasil tiga data pertama yang ditampilkan seperti berikut.

Terlihat hanya tiga baris data pertama yang ditampilkan dari keseluruhan sepuluh baris data yang ada.

Tugas:
Ambillah lima data teratas dari kolom nama_produk dan harga.

Jika perintah yang diketikkan berjalan dengan benar, maka Live Code Editor Console akan menampilkan hasil seperti berikut.

Jawaban:
select nama_produk, harga from ms_produk limit 5

## Penggunaan SELECT DISTINCT statement

Aku diminta mengambil data dari tabel ms_pelanggan oleh Senja. Menggunakan perintah yang telah dipelajari, aku menuliskan Syntax pada Live Code Editor:

Ternyata, dari data pelanggan, aku menemukan duplikasi data, dalam nama_customer dan alamat untuk no_urut 3 & 11, serta 5 & 12 yang sama persis dengan kode_pelanggan yang berbeda. Tentunya ini akan berdampak pada hasil analisaku nantinya.

Untuk menghilangkan data duplikasi, aku bisa menggunakan SELECT DISTINCT statement. Dengan SELECT DISTINCT, data yang sama atau duplikat akan dieliminasi dan akan ditampilkan data yang unik saja.

Berikut syntax-nya:

Aku langsung mempraktikkan syntax SELECT DISTINCT untuk mengambil data pelanggan dan menghilangkan duplikasi data.

Tugas:
Tampilkan nama_customer dan alamat dari tabel ms_pelanggan dan hilangkan data duplikat. Jika benar, maka Live Code Editor akan menampilkan tabel seperti berikut pada console.

Jika dihitung jumlah row data yang berbeda maka diperoleh ada 10 row data berbeda dari tabel ms_pelanggan.

Jawaban:
select distinct nama_customer, alamat from ms_pelanggan
