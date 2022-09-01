## Produk DQLab Mart

Mengacu pada table ms_produk, tampilkan daftar produk yang memiliki harga antara 50.000 and 150.000.

Nama kolom yang harus ditampilkan: no_urut, kode_produk, nama_produk, dan harga.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select no_urut, kode_produk, nama_produk, harga from ms_produk where harga between 50000 and 150000

## Thumb drive di DQLab Mart

Tampilkan semua produk yang mengandung kata Flashdisk.

Nama kolom yang harus ditampilkan: no_urut, kode_produk, nama_produk, dan harga.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select no_urut, kode_produk, nama_produk, harga from ms_produk where nama_produk LIKE '%Flashdisk%'

## Pelanggan Bergelar

Tampilkan hanya nama-nama pelanggan yang hanya memiliki gelar-gelar berikut: S.H, Ir. dan Drs.

Nama kolom yang harus ditampilkan: no_urut, kode_pelanggan, nama_pelanggan, dan alamat.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select \* from ms_pelanggan where nama_pelanggan like '%S.H%' or nama_pelanggan like '%Ir.%' or nama_pelanggan like '%Drs.%'

## Mengurutkan Nama Pelanggan

Tampilkan nama-nama pelanggan dan urutkan hasilnya berdasarkan kolom nama_pelanggan dari yang terkecil ke yang terbesar (A ke Z).

Nama kolom yang harus ditampilkan: nama_pelanggan.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select nama_pelanggan from ms_pelanggan order by nama_pelanggan

## Mengurutkan Nama Pelanggan Tanpa Gelar

Tampilkan nama-nama pelanggan dan urutkan hasilnya berdasarkan kolom nama_pelanggan dari yang terkecil ke yang terbesar (A ke Z), namun gelar tidak boleh menjadi bagian dari urutan. Contoh: Ir. Agus Nugraha harus berada di atas Heidi Goh.

Nama kolom yang harus ditampilkan: nama_pelanggan.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select nama_pelanggan from ms_pelanggan ORDER BY SUBSTRING_INDEX (nama_pelanggan, '. ', -1)

## Nama Pelanggan yang Paling Panjang

Tampilkan nama pelanggan yang memiliki nama paling panjang. Jika ada lebih dari 1 orang yang memiliki panjang nama yang sama, tampilkan semuanya.

Nama kolom yang harus ditampilkan: nama_pelanggan.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

SELECT nama_pelanggan FROM ms_pelanggan WHERE LENGTH(nama_pelanggan) in (select max(length(nama_pelanggan)) from ms_pelanggan)

## Nama Pelanggan yang Paling Panjang dengan Gelar

Tampilkan nama orang yang memiliki nama paling panjang (pada row atas), dan nama orang paling pendek (pada row setelahnya). Gelar menjadi bagian dari nama. Jika ada lebih dari satu nama yang paling panjang atau paling pendek, harus ditampilkan semuanya.

Nama kolom yang harus ditampilkan: nama_pelanggan.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

SELECT nama_pelanggan
FROM ms_pelanggan WHERE (length(nama_pelanggan) in (select min(length(nama_pelanggan)) from ms_pelanggan)) or (length(nama_pelanggan) in (select max(length(nama_pelanggan)) from ms_pelanggan))
ORDER BY length(nama_pelanggan) desc;

## Kuantitas Produk yang Banyak Terjual

Tampilkan produk yang paling banyak terjual dari segi kuantitas. Jika ada lebih dari 1 produk dengan nilai yang sama, tampilkan semua produk tersebut.

Nama kolom yang harus ditampilkan: kode_produk, nama_produk,total_qty.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select ms_produk.kode_produk, ms_produk.nama_produk,sum(tr_penjualan_detail.qty) as total_qty
from ms_produk
inner join tr_penjualan_detail
on ms_produk.kode_produk = tr_penjualan_detail.kode_produk
group by ms_produk.kode_produk, ms_produk.nama_produk
HAVING SUM(tr_penjualan_detail.qty) > 2;

##

Pelanggan Paling Tinggi Nilai Belanjanya

Siapa saja pelanggan yang paling banyak menghabiskan uangnya untuk belanja? Jika ada lebih dari 1 pelanggan dengan nilai yang sama, tampilkan semua pelanggan tersebut.

Nama kolom yang harus ditampilkan: kode_pelanggan, nama_pelanggan, total_harga.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select ms_pelanggan.kode_pelanggan, ms_pelanggan.nama_pelanggan, sum(tr_penjualan_detail.qty\*tr_penjualan_detail.harga_satuan) as total_harga
from ms_pelanggan
inner join tr_penjualan ON ms_pelanggan.kode_pelanggan = tr_penjualan.kode_pelanggan
inner join tr_penjualan_detail ON tr_penjualan.kode_transaksi = tr_penjualan_detail.kode_transaksi
group by ms_pelanggan.kode_pelanggan, ms_pelanggan.nama_pelanggan
order by total_harga desc
limit 1

## Pelanggan yang Belum Pernah Berbelanja

Tampilkan daftar pelanggan yang belum pernah melakukan transaksi.

Nama kolom yang harus ditampilkan: kode_pelanggan, nama_pelanggan, alamat.

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

select
ms_pelanggan.kode_pelanggan,
ms_pelanggan.nama_pelanggan,
ms_pelanggan.alamat
from ms_pelanggan
WHERE kode_pelanggan NOT IN (SELECT tr_penjualan.kode_pelanggan FROM tr_penjualan);

## Transaksi Belanja dengan Daftar Belanja lebih dari 1

Tampilkan transaksi-transaksi yang memiliki jumlah item produk lebih dari 1 jenis produk. Dengan lain kalimat, tampilkan transaksi-transaksi yang memiliki jumlah baris data pada table tr_penjualan_detail lebih dari satu.

Nama kolom yang harus ditampilkan: kode_transaksi, kode_pelanggan, nama_pelanggan, tanggal_transaksi, jumlah_detail

Semua table di atas sudah tersedia, Anda tinggal menulis query Anda dalam Code Editor.

SELECT tr_penjualan.kode_transaksi,
tr_penjualan.kode_pelanggan,
ms_pelanggan.nama_pelanggan,
tr_penjualan.tanggal_transaksi,
COUNT(tr_penjualan_detail.qty) AS jumlah_detail
FROM tr_penjualan INNER JOIN ms_pelanggan ON tr_penjualan.kode_pelanggan = ms_pelanggan.kode_pelanggan
INNER JOIN tr_penjualan_detail ON tr_penjualan.kode_transaksi = tr_penjualan_detail.kode_transaksi
GROUP BY tr_penjualan.kode_transaksi, tr_penjualan.kode_pelanggan, ms_pelanggan.nama_pelanggan, tr_penjualan.tanggal_transaksi
HAVING jumlah_detail > 1;
