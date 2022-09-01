## Fungsi Text - CONCAT( )

Fungsi CONCAT()

Syntax:

SELECT CONCAT(ColumnName1, ColumnName2, ColumnNameN)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select studentid, concat(firstname, lastname) as name, semester1, semester2, markgrowth from students

## Fungsi Text - SUBSTRING_INDEX( )

Fungsi Text SUBSTRING_INDEX()

Syntax:

SELECT SUBSTRING_INDEX(column, delimiter, index to return)  
FROM TableName;
Keterangan:

     column --> merupakan nama kolom yang akan dipecah text-nya,

     delimiter --> karakter atau gabungan beberapa karakter untuk pemecah text pada kolom bersangkutan,

     index_to_return --> indeks dari pecahan text yang akan diambil.

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

+-----------+---------------+
| StudentID | Name |
+-----------+---------------+
| 1 | Jose_Mohit |
| 2 | lala_karlina |
| 3 | Sultan_Hadi |
| 4 | jaya_usman |
| 5 | anjali_wijaya |
+-----------+---------------+
Di sini terlihat bagaimana mengambil pecahan text pertama (1) atau sub-text sebelum delimiter '@'.

Jawaban:
select studentid, substring_index(email,'@',1) as name from students

## Fungsi Text - SUBSTR( )

Fungsi Text SUBSTR()

Syntax:

SELECT SUBSTR(columnName, Start Index, Number of string to be extract)
FROM TableName;
Keterangan:

     columnName --> nama kolom yang akan dicari substring-nya

     Start Index --> indeks dari text yang dimiliki (dimulai dari 1)

     Number of string to be extract --> jumlah karakter atau beberapa karakter yang akan diambil.

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Pada contoh ini bisa dilihat aku mengambil substring mulai pada karakter ke dua hingga karakter ke empat.

Jawaban:
select studentid, substr(firstname, 2, 3) as initial from students

## Fungsi Text - LENGTH( )

Fungsi Text LENGTH()

Syntax:

SELECT LENGTH(ColumnName)
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select studentid, firstname, length(firstname) as total_char from students

## Fungsi Text - REPLACE( )

Fungsi Text REPLACE()

Syntax:

SELECT REPLACE(ColumnName, Character/String to be change, New String/Character)
FROM TableName;
Keterangan:

     ColumnName --> nama kolom yang akan diganti isi tiap record/barisnya berdasarkan string/karakter tertentu

     Character/String to be change --> string/karakter yang dimiliki untuk diganti

     New String/Character --> string/karakter baru pengganti string/karakter sebelumnya

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

+-----------+-------------------------+-------------------------+
| StudentID | Email | New_Email |
+-----------+-------------------------+-------------------------+
| 1 | Jose_Mohit@gmail.com | Jose_Mohit@gmail.com |
| 2 | lala_karlina@yahoo.com | lala_karlina@gmail.com |
| 3 | Sultan_Hadi@gmail.com | Sultan_Hadi@gmail.com |
| 4 | jaya_usman@yahoo.com | jaya_usman@gmail.com |
| 5 | anjali_wijaya@yahoo.com | anjali_wijaya@gmail.com |
+-----------+-------------------------+-------------------------+
Pada tabel ini terlihat bahwa semua email yang sebelumnya dengan domain yahoo telah berubah menjadi gmail.

Jawaban:
select studentid, email, replace(email, 'yahoo', 'gmail') as new_email from students

## Tugas Praktek

Tugas:
Gunakan fungsi UPPER() untuk mengubah kolom FirstName menjadi seluruhnya kapital dan gunakan LOWER() untuk mengubah kolom LastName menjadi seluruhnya non-kapital. Gunakan kedua fungsi tersebut dalam satu SELECT-Statement.

Jika berhasil, berikut output tabel yang diperoleh:

Jawaban:
select studentid, upper(firstname) as firstname, lower(lastname) as lastname from students
