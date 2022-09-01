## Tugas Praktek

Cobalah ketik query pada code editor untuk melihat keseluruhan isi dari kolom tabel ms_item_kategori dan ms_item_warna.

Jika berjalan dengan benar query-nya dan kemudian berjalan dengan lancar maka akan mendapatkan hasil berikut:

Jawaban:
select _ from ms_item_kategori;
select _ from ms_item_warna

## Menggabungkan Tabel dengan Key Columns

Saatnya mempraktekkan penggabungan tabel ms_item_kategori dan ms_item_warna menggunakan key columns.

Cobalah tuliskan query berikut di code editor:

Jika query yang ditunjukkan dengan benar diketikkan maka akan mendapatkan hasil berikut setelah menekan tombol .

Dapat dilihat hasil dari penggabungan dua tabel tersebut yaitu berupa tabel baru dengan empat kolom dan enam baris data. Perlu diketahui bahwa penggabungan ini bersifat sementara artinya tabel asli di database tidak mengalami perubahan, dan tabel baru hasil penggabungan ini juga tidak serta merta tersimpan di database.

Jawaban:
select \* from ms_item_kategori, ms_item_warna where nama_barang = nama_item

## Bagaimana jika urutan Tabel diubah?

Jika akan mengubah urutan tabel di bagian FROM pada query inner join, maka hanya urutan kolom saja yang berubah tetapi isi data dan jumlah data tidak berubah.

Mari lihat contohnya dengan mengganti query yang sebelumnya, yaitu:

Menjadi query seperti ini

Ketikkan query yang terakhir ini pada code editor dan jalankan dengan menekan tombol . Jika berhasil maka akan menampilkan hasil berikut.

Terlihat jumlah data yang dihasilkan tetap 6 baris data, namun dengan urutan kolom yang berbeda.

Dimana dua kolom pertama adalah dari tabel ms_item_warna, dan dua kolom berikutnya dari tabel ms_item_kategori. Hal ini sesuai dengan urutan nama tabel yang diketikkan setelah FROM.

Jawaban:
select \* from ms_item_warna, ms_item_kategori where nama_barang=nama_item

## Menggunakan Prefix Nama Tabel

Seperti yang dijelaskan sebelumnya, jika akan menggunakan wildcard (\*), dan tidak menentukan spesifik nama kolom yang akan dimunculkan di bagian SELECT, maka secara default urutan kolom dimulai dengan kolom dari tabel yang dinyatakan pertama di bagian FROM. Akan tetapi, bisa juga memanfaatkan wildcard dengan menambahkan prefix nama tabel, dimana dengan merinci prefix nama tabel ini, dimungkinkan untuk menentukan urutan kolom dari tabel mana yang muncul duluan.

Jika lupa dapat mengacu kembali ke Modul: Fundamental SQL Using SELECT Statement, Chapter: Prefix dan Alias.

Sebagai contoh, jika akan menggabungkan kedua tabel, dengan menyatakan tabel ms_item_warna terlebih dahulu di bagian FROM, tetapi yang ingin dimunculkan kolomnya di awal hasil adalah dari yang ms_item_kategori, maka querynya akan menjadi sebagai berikut.

Jika query yang diketikkan sesuai dengan yang ditunjukkan dan berhasil dijalankan maka akan diperoleh hasil berikut ini:

Terlihat urutan kolom yang muncul adalah dari tabel ms_item_kategori terlebih dahulu.

Jawaban:
select ms*item_kategori.*, ms*item_warna.* from ms_item_warna, ms_item_kategori where nama_barang = nama_item

## Penggabungan Tanpa Kondisi

Sesuai dugaanku. Aku kembali menemukan hal yang membingungkan. Dan, tampaknya hari ini Senja memang sudah mendedikasikan waktunya untuk mengajariku karena (beruntungnya!) Senja masih tepat di sebelahku.

“Nja, hehehe. Sorry mau ganggu lagi. Bagaimana kalau aku ingin menggabungkan tabel tanpa ada kondisi? Apakah tetap bisa memakai metode ini?”

Senja memicingkan matanya pada layar laptop yang kutunjuk sebelum menjawab. “Pertanyaan bagus. Penjelasan dan praktek yang kita lakukan pada materi sebelumnya adalah penggabungan dua tabel dengan menggunakan kondisi, yaitu terdapat data yang sama pada key kolom dari kedua tabel. Akan tetapi, memang benar, dalam beberapa case di real problem, sering kali terdapat permasalahan tertentu dimana kita ingin menggabungkan tabel tanpa ada kondisi. Proses penggabungan ini juga dapat dilakukan dengan metode koma dan tanpa menggunakan kondisi relasi antar kolom.”

Aku mencoba mencerna penjelasan Senja. Sebelum aku sempat memahami semuanya. Senja sudah mengajakku untuk melihat contoh.

“Berikut adalah contoh query dari penggabungan seperti itu.”

“Terlihat pada query kita hanya menyertakan nama dua tabel yang akan diambil datanya, tapi tidak ada informasi kondisi bagaimana kedua tabel tersebut berelasi satu dengan yang lainnya melalui key column. Lalu apa hasilnya?” tanya Senja retoris.

“Kamu hanya butuh untuk mengetik query ini pada code editor dan jalankan, jika berhasil dengan baik maka akan muncul hasil dengan enam puluh empat baris data seperti berikut.”

Aku memperhatikan dengan saksama. Jangan sampai ada yang terlewat!

+-----------+----------+-------------+--------------+
| nama_item | kategori | nama_barang | warna |
+-----------+----------+-------------+--------------+
| bayam | sayuran | apel | merah |
| belimbing | buah | apel | merah |
| duku | buah | apel | merah |
| durian | buah | apel | merah |
| gandum | buah | apel | merah |
| jamur | sayuran | apel | merah |
| jambu air | buah | apel | merah |
| jeruk | buah | apel | merah |
| bayam | sayuran | bayam | hijau |
| belimbing | buah | bayam | hijau |
| duku | buah | bayam | hijau |
| durian | buah | bayam | hijau |
| gandum | buah | bayam | hijau |
| jamur | sayuran | bayam | hijau |
| jambu air | buah | bayam | hijau |
| jeruk | buah | bayam | hijau |
| bayam | sayuran | daun bawang | hijau |
| belimbing | buah | daun bawang | hijau |
| duku | buah | daun bawang | hijau |
| durian | buah | daun bawang | hijau |
| gandum | buah | daun bawang | hijau |
| jamur | sayuran | daun bawang | hijau |
| jambu air | buah | daun bawang | hijau |
| jeruk | buah | daun bawang | hijau |
| bayam | sayuran | duku | kuning pekat |
| belimbing | buah | duku | kuning pekat |
| duku | buah | duku | kuning pekat |
| durian | buah | duku | kuning pekat |
| gandum | buah | duku | kuning pekat |
| jamur | sayuran | duku | kuning pekat |
| jambu air | buah | duku | kuning pekat |
| jeruk | buah | duku | kuning pekat |
| bayam | sayuran | durian | kuning |
| belimbing | buah | durian | kuning |
| duku | buah | durian | kuning |
| durian | buah | durian | kuning |
| gandum | buah | durian | kuning |
| jamur | sayuran | durian | kuning |
| jambu air | buah | durian | kuning |
| jeruk | buah | durian | kuning |
| bayam | sayuran | gandum | coklat |
| belimbing | buah | gandum | coklat |
| duku | buah | gandum | coklat |
| durian | buah | gandum | coklat |
| gandum | buah | gandum | coklat |
| jamur | sayuran | gandum | coklat |
| jambu air | buah | gandum | coklat |
| jeruk | buah | gandum | coklat |
| bayam | sayuran | jambu air | merah |
| belimbing | buah | jambu air | merah |
| duku | buah | jambu air | merah |
| durian | buah | jambu air | merah |
| gandum | buah | jambu air | merah |
| jamur | sayuran | jambu air | merah |
| jambu air | buah | jambu air | merah |
| jeruk | buah | jambu air | merah |
| bayam | sayuran | jeruk | oranye |
| belimbing | buah | jeruk | oranye |
| duku | buah | jeruk | oranye |
| durian | buah | jeruk | oranye |
| gandum | buah | jeruk | oranye |
| jamur | sayuran | jeruk | oranye |
| jambu air | buah | jeruk | oranye |
| jeruk | buah | jeruk | oranye |
+-----------+----------+-------------+--------------+

Aku menggumam mengerti. Terlihat banyak sekali hasil yang keluar, ini dikarenakan setiap baris data pada kedua tabel akan dihubungkan satu sama lain - tanpa ada hubungan.

Jumlah enam puluh empat baris data ini adalah hasil perkalian dari jumlah data dari kedua tabel, dimana masing-masing memiliki delapan baris data. Cara menggabungkan kedua tabelseperti ini disebut dengan mekanisme cross join.

Aku sudah sampai di penghujung materi dan sejauh ini cukup paham! Hanya butuh satu kuis lagi untuk menuntaskannya. Belajar memang jadi lebih mudah kalau ada Senja, eh maksudku mentor, hehehe.

Jawaban:
select \* from ms_item_kategori, ms_item_warna
