## Fungsi Aggregate - SUM()

Fungsi Aggregate SUM()

Syntax:

SELECT SUM(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketikanlah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select sum(semester1) as total_1, sum(semester2) as total_2 from students

## Fungsi Aggregate - COUNT()

Fungsi Aggregate COUNT()

Syntax:

SELECT COUNT(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select count(firstname) as total_student from students

## Fungsi Aggregate - AVG( )

Fungsi Aggregate AVG()

Syntax:

SELECT AVG(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select avg(semester1) as avg_1, avg(semester2) as avg_2 from students

## Tugas Praktek

Tugas:
Setelah memahami fungsi-fungsi sebelumnya, kali ini Senja memintaku untuk menggunakan fungsi MIN() dan MAX() untuk menghitung nilai dari kolom Semester1 dan Semester2. Aku menggunakan fungsi tersebut dalam satu SELECT-Statement.

Jika berhasil, berikut output tabel yang diperoleh:

Jawaban:
select min(semester1) as min1, max(semester1) as max1, min(semester2) as min2, max(semester2) as max2 from students

## Group by Single Column

Fungsi Group by Single Column memastikan data dapat dikelompokkan menggunakan kriteria dari satu kolom saja, misalnya mengelompokkan data berdasarkan provinsi saja.

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Jawaban:
select province, count(distinct order_id) as total_order, sum(item_price) as total_price from sales_retail_2019 group by province

## Group by Multiple Column

Dengan fungsi Group by Multiple Column, data dapat dikelompokkan menggunakan kriteria dari dua kolom atau lebih, misalnya mengelompokkan data berdasarkan province dan brand.

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Jawaban:
select province, brand, count(distinct order_id) as total_order, sum(item_price) as total_price from sales_retail_2019 group by province, brand

## Fungsi Aggregate dengan Grouping

“Tambahan lagi, Aksara. Kamu masih ingatkan fungsi agregasi yang kita pelajari dan praktikkan sebelumnya? Pada fungsi itu kita belum menggunakan group by sehingga hasil SUM dan COUNT kita adalah hasil SUM dan COUNT dari seluruh baris yang ada di tabel data penjualan.”

“Ada data penjualannya kah, Nja? Biar lebih mudah membayangkan dan mempraktikkannya,” usulku.

Senja membuka data penjualan perusahaan tahun lalu untukku. Wow!

“Kalau begitu, kita praktik langsung saja. Sekarang coba kamu gunakan fungsi agregasi dan GROUP BY untuk menghitung total penjualan dari setiap provinsi di tahun 2019, dan kita bandingkan dengan hasil fungsi agregasi tanpa menggunakan group by,” pinta Senja.

Contoh aggregate dengan grouping:

Tugas:
Ketikkan query di atas pada live code editor, jika berhasil maka akan menghasilkan output berikut:

Jawaban:
select province, count(distinct order_id) as total_unique_order, sum(item_price) as revenue from sales_retail_2019 group by province

## Tugas Praktek

Tugas:
Dengan menggunakan data sales_retail_2019, buatlah syntax query yang menggunakan fungsi skalar MONTH() untuk mengubah order_date dari tanggal ke bulan, fungsi aggregate SUM() untuk menjumlahkan kolom item_price.

Tambahkan kolom remark menggunakan CASE… WHEN… statement. Jika sum(item_price) >= 30.000.000.000, maka remark-nya 'Target Achieved'; Jika sum(item_price) <= 25.000.000.000 maka remark-nya 'Less performed'; Selain itu, beri remark 'Follow Up'.

Tugas:
Gantilah tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang dideskripsikan pada soal di atas.

Jika berhasil, tabel yang akan muncul adalah seperti berikut ini:

Akhirnya selesai juga! Ini latihan modulku yang terakhir untuk materi hari ini. Berkat bimbingan Senja yang mengkombinasikan penjelasan dan praktik, aku jadi lebih paham bagaimana melakukan operasi numerik dengan fungsi agregat dan operasi text/string dengan fungsi skalar di SQL; serta bagaimana cara penggunaannya dengan group by statement dan CASE… WHEN... statement.

“Ah, enggak sesusah yang kukira!” gumamku bersemangat.

Jawaban:
SELECT month(order_date) AS order_month, sum(item_price) AS total_price,
CASE  
 WHEN sum(item_price) >= 30000000000 THEN 'Target Achieved'
WHEN sum(item_price) <= 25000000000 THEN 'Less Performed'
ELSE 'Follow Up'
END as remark
FROM sales_retail_2019
GROUP BY order_month;
