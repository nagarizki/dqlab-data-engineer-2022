## Menggunakan Prefix pada Nama Kolom

“Agar kamu lebih jelas, saya coba praktikkan untuk kamu ya, Aksara. Pertama, kita mulai dengan menggunakan prefix pada kolom. Pada dasarnya, penulisan nama kolom yang lengkap perlu mencantumkan nama tabel di depan nama kolom tersebut, dengan tanda penyambung berupa tanda titik. Umumnya, jika kita hanya mengambil kolom dari satu tabel, prefix ini jarang digunakan karena sudah jelas dari tabel mana kolom itu berasal. Tetapi ketika kita mengambil data dari dua tabel, misalnya dengan menggabungkan 2 tabel menggunakan JOIN, dan terdapat 2 kolom dengan nama yang sama, maka penggunaan prefix menjadi penting untuk menghindari error karena ambiguitas,” jelas Senja panjang lebar.

Aku masih menyimak pada layar laptop Senja yang menunjukkan syntax dasar dari penggunaan prefix pada nama kolom.

Untuk mengambil nama kolom nama_produk data dari tabel ms_produk dengan penulisan prefix nama tabel adalah sebagai berikut.

Jika berjalan dengan lancar maka akan mendapatkan hasil berikut.

Penggunaan nama lengkap prefix ini akan sangat berguna ketika ingin mengidentifikasi data dari beberapa tabel, yang akan dipelajari pada course SQL untuk topik JOIN.

Tugas:
Gantilah seluruh code yang ada pada code editor dengan perintah SELECT untuk menampilkan kolom kode_produk dari tabel ms_produk dengan penulisan menggunakan prefix nama tabel.

Jika berjalan dengan lancar maka hasilnya akan terlihat sebagai berikut.

Jawaban:
select ms_produk.kode_produk from ms_produk

## Menggunakan Alias pada Kolom

Selain prefix, aku dapat mengubah identitas nama kolom yang diambil dengan SELECT dengan menggunakan keyword AS. Ini dinamakan alias. Perubahan nama tabel bersifat temporary, artinya hanya berubah ketika mengambil/meng-query data, sedangkan nama kolom di tabel dalam database tidak akan berubah.

Berikut adalah contoh untuk mengubah nama kolom dari kode_produk menjadi product_code dari table ms_produk.

Ketik dan jalankan code tersebut pada code editor, jika berjalan dengan lancar akan muncul hasil sebagai berikut.

Terlihat kolom kode_produk telah berubah nama menjadi product_code.

Catatan: alias tidak bisa digunakan untuk wildcard (\*)

Tugas:
Coba ubah perintah SELECT di atas untuk mengubah nama kolom dengan details berikut:

no_urut menjadi nomor.
nama_produk menjadi nama.
Jika berjalan lancar, maka akan muncul hasil berikut.

Jawaban:
select no_urut as nomor, nama_produk as nama from ms_produk

## Menghilangkan Keyword 'AS'

Keyword AS yang digunakan sebagai penanda alias pada kolom dapat dihilangkan dengan syntax:

Berikut adalah contoh yang sama dari sub-chapter sebelumnya, dimana untuk mengubah nama kolom dari kode_produk menjadi product_code dari tabel ms_produk dapat dilakukan tanpa menggunakan alias.

Cobalah jalankan, dan hasilnya akan terlihat sebagai berikut.

Tugas:
Ubah nama kolom dari tabel ms_produk tanpa menggunakan Alias:

no_urut menjadi nomor.
nama_produk menjadi nama.
Jika berjalan lancar, maka Live Code Editor akan menampilkan hasil berikut:

Jawaban:
select no_urut nomor, nama_produk nama from ms_produk

## Menggabungkan Prefix dan Alias

Prefix dan alias juga dapat digunakan secara bersamaan.

Aku menerapkannya dengan tabel ms_produk, menggunakan prefix nama tabel dan alias untuk merubah nama_produk menjadi nama.

Jika berjalan dengan lancar, maka akan muncul hasil berikut.

Tugas:
Tampilkan kolom harga dari tabel ms_produk dengan nama alias harga_jual lengkap dengan prefix.

Jika berjalan dengan lancar, Live Code Editor akan mengeluarkan hasil sebagai berikut.

Jawaban:
select ms_produk.harga as harga_jual from ms_produk

## Menggunakan Alias pada Tabel

Selain kolom, nama alias juga bisa digunakan untuk tabel dengan menggunakan keyword AS setelah nama tabel. Dan, keyword ini juga bisa digunakan atau tidak. Umumnya penggunaan alias pada tabel jika nama tabel tersebut cukup panjang dan muncul atau dirujuk beberapa kali dalam query. Sehingga dengan menggunakan alias pada tabel, dapat menghemat waktu dalam menuliskan query, khususnya untuk query yang cukup rumit, panjang dan melibatkan banyak tabel.

Penulisannya adalah sebagai berikut.

Berikut adalah contoh untuk menggunakan alias pada tabel ms_produk menjadi t1.

Jika berjalan dengan lancar maka akan memberi hasil berikut.

Terlihat hasil yang dikeluarkan adalah seluruh isi tabel ms_produk.

Tugas:
Ganti nama tabel ms_produk menjadi t2 dan tampilkan seluruh isinya tanpa menggunakan keyword AS.

Jawaban:
select \* from ms_produk t2

## Prefix dengan Alias Tabel

Aku menyela sebentar penjelasan Senja karena masih penasaran mengenai Prefix ini.

“Nja, kalau kita menggunakan alias tabel, maka nama prefix yang digunakan untuk kolom adalah alias tabel dan bukan nama original tabel, seperti yang ditunjukkan berikut ini. Gimana hasilnya?”

“Penggunaan nama original tabel sebagai prefix akan menimbulkan error saat query dijalankan karena dengan penggunaan alias, nama tabel secara temporary sudah di-gantikan oleh alias, Aksara,” jawab Senja lugas.

Aku mengangguk. Senja pun kembali melanjutkan penjelasannya.

Mari lihat contoh berikut ini dari tabel ms_produk yang telah digunakan sebelumnya

Jalankan dan jika berhasil dengan baik maka akan memunculkan hasil berikut.

Jika kolom dan tabel memiliki alias, dapat dilakukan dengan mengetikkan perintah berikut di code editor

“Oke, Nja. Sekarang aku sudah paham syntax query,” ujarku bersemangat.

Dari apa yang ditunjukkan Senja, aku bisa mengetahui kalau Senja menggunakan alias tabel yaitu t1, prefix untuk kolom adalah t1, dan alias untuk nama kolom. Maka itu, hasil yang diperoleh dengan menjalankan query adalah seperti ini:

Tugas:
Gantilah perintah pada code editor dengan nama alias t2 - tanpa menggunakan keyword AS - untuk tabel ms_produk dan menampilkan kolom nama_produk dan harga, lengkap dengan prefix alias.

Jika berjalan dengan lancar maka akan memunculkan hasil berikut.

Jawaban:
select t2.nama_produk, t2.harga from ms_produk t2
