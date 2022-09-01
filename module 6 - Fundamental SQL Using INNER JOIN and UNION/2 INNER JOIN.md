## Tugas Praktek: Menggunakan INNER JOIN (1/3)

Sejauh ini aku belum memiliki pertanyaan berarti dan semoga saja tidak ada. Dalam hati kuberdoa kelancaran pembelajaran ini juga sampai ke kuis dan tugasnya, hehehe.

“Kita lanjut penjelasannya ya, Aksara,” ujar Senja menarikku kembali ke materi.

“Nah, sebelumnya kan kita sudah menerapkan penggunaan … WHERE …; dari perintah SELECT … dan operator koma, untuk penggabungan tabel ms_item_warna dan ms_item_kategori. Selanjutnya, ini kita akan menggunakan klausa INNER JOIN … ON …; untuk menggabungkan kedua ms_item_warna dan ms_item_kategori berdasarkan sintaks INNER JOIN yang telah dijelaskan sebelumnya.”

Silakan ketikkan query berikut pada code editor

Jika dijalankan dan tidak ada kesalahan pada penulisan query-nya, maka hasilnya akan terlihat sebagai berikut.

Hasil yang diperoleh dengan penggunaan SELECT … FROM … INNER JOIN … ON …; adalah sama dengan penerapan SELECT … FROM … WHERE …;.

Jawaban:
select \* from ms_item_warna
inner join ms_item_kategori
on ms_item_warna.nama_barang = ms_item_kategori.nama_item

## tabel tr_penjualan dan tabel ms_produk

Tak kusangka penggunaan INNER JOIN ini banyak sekali langkah per langkahnya. Untungnya aku sudah diberi modul oleh Senja, kalau tidak, buku catatanku bisa habis diisi oleh materi ini saja.

“Setelah kita menggunakan tabel ms_item_warna dan ms_item_kategori, sekarang mari kita gunakan tabel tr_penjualan dan tabel ms_produk yang ada di-database, sehingga kita bisa lebih paham mengenai penerapan konsep JOIN di real case,” pinta Senja.

“Oke, Nja.”

”Mari kita lihat isi dari tabel tr_penjualan. Silakan ketikkan query berikut pada code editor.”

Jika dijalankan dan tidak ada kesalahan pada sintaks, maka hasilnya akan terlihat sebagai berikut.

Jawaban:
select _ from tr_penjualan;
select _ from ms_produk

## Tugas Praktek: Menggunakan INNER JOIN (2/3)

“Oke, Aksara. Silakan dipraktikkan pada code editor untuk menggabungkan tabel tr_penjualan dan ms_produk dan menampilkan seluruh kolom dari kedua tabel.”

Aku mengecek lagi beberapa coretan penting materi tadi dan mulai mengerjakan kode-nya. Jika dijalankan berikutlah hasilnya

Jawaban:
select \* from tr_penjualan inner join ms_produk on tr_penjualan.kode_produk = ms_produk.kode_produk

## Tugas Praktek: Menggunakan INNER JOIN (3/3)

“Oke, semua dariku sudah. Sekarang silakan dipraktikkan pada code editor untuk menggabungkan tabel tr_penjualan dan ms_produk dengan kolom yang ditampilkan dari tabel tr_penjualan adalah kode_transaksi, kode_pelanggan, kode_produk, qty. Untuk tabel ms_produk tampilkan kolom nama_produk dan harga."

Aku mengangguk mantap. Senja sudah membekaliku sampai di sini. Ini saatnya aku mandiri.

Kemudian aku membentuk kolom total yang merupakan hasil perkalian setiap baris pada kolom harga di tabel ms_produk dengan kolom qty di tabel tr_penjualan.

"Tabel hasil penggabungan haruslah membentuk kolom-kolom dengan urutannya adalah kode_transaksi, kode_pelanggan, kode_produk, nama_produk, harga, qty, dan total," lanjut Senja lagi mengingatkan.

Jawaban:
SELECT tr_penjualan.kode_transaksi, tr_penjualan.kode_pelanggan, tr_penjualan.kode_produk, ms_produk.nama_produk, ms_produk.harga, tr_penjualan.qty, ms_produk.harga \* tr_penjualan.qty as total
FROM tr_penjualan
INNER JOIN ms_produk
ON tr_penjualan.kode_produk = ms_produk.kode_produk
