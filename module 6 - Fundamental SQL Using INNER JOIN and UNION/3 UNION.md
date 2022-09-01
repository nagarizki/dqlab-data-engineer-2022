## Tabel yang Akan Digabungkan

“Oke, pertama - tama mari kita SELECT seluruh kolom dari tabel_A.” Aku memperhatikan intruksi pertama Senja.

“Selanjutnya kita SELECT seluruh kolom dari tabel_B,” tambah Senja.

Dan, hasilnya seperti ini :

Sesuai dengan syarat untuk penggabungan dengan UNION yang telah dijelaskan tadi bahwa:

jumlah kolom tabel_A dan tabel_B adalah sama
kolom-kolom pada tabel_A dan tabel_B memiliki tipe data yang sama, dan
kolom-kolom pada tabel_A dan tabel_B memiliki urutan posisi yang sama.
Melalui pengecekan pada tabel_A dan tabel_B pastikan bahwa ketiga syarat penggabungan dengan UNION yang dinyatakan di atas terpenuhi. Langkah ini kita lakukan sebelum melanjutkan pada praktek berikutnya menggunakan UNION.

Jawaban:
select _ from tabel_a;
select _ from tabel_b

## Menggunakan UNION

Kedua tabel_A dan tabel_B sudah memiliki jumlah kolom yang sama, dan juga urutan posisi kolom juga sama, jadi bisa langsung menggabungkan kedua kolom tersebut dengan menambahkan UNION.

Ketikkanlah kode berikut di code editor:

Jika query yang ku ketikkan benar dan kemudian dijalankan tabel penggabungan yang ku peroleh ditujukkan sebagai berikut :

Jawaban:
select _ from tabel_a union
select _ from tabel_b

## Menggunakan UNION dengan Klausa WHERE

Aku bertanya pada Senja, “Terus, kalo ada kondisi WHERE, syntaxnya bagaimana? Misalnya aku hanya ingin menggabungkan tabel yang isinya data penjualan untuk kode produk prod-04 saja?”

”Mudah saja, tinggal tambahkan WHERE di kedua SELECT-statement, seperti berikut ini,”

Jika query-nya dengan benar dituliskan dan kemudian dijalankan maka akan diperoleh:

Tugas Praktek:

Lakukanlah hal yang sama dengan yang dicontohkan, akan dipilih kode_pelanggan = 'dqlabcust03' sebagai kondisinya.

Jika query-nya diketikkan dengan benar maka tabel penggabungan yang tampil dengan kondisi kode_pelanggan = 'dqlabcust03' adalah:

Jawaban:
select _ from tabel_a
where kode_pelanggan = 'dqlabcust03'
union
select _ from tabel_b
where kode_pelanggan = 'dqlabcust03'

## Menggunakan UNION dan Menyelaraskan Kolom-Kolomnya.

Senja menyerahkan tugas praktik sederhana untuk menguji materi ini. Sekilas kubaca pertanyaan dan perintahnya tidak sulit. Baiklah, mari langsung terapkan ilmunya!

Ketikkan syntax query di bawah pada Code Editor, untuk melihat hasil dari penggabungan tabel (UNION) dengan menyelaraskan kolom.

Jika berhasil maka hasil nya akan seperti berikut ini:

Jawaban:
select customername, contactname, city, postalcode from customers
union
select suppliername, contactname, city, postalcode from suppliers
