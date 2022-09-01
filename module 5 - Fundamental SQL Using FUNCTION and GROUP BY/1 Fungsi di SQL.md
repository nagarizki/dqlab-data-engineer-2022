## Fungsi Skalar Matematika - ABS()

Fungsi ABS( )

Syntax:

SELECT ABS(ColumnName)  
FROM TableName;
Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas dengan live code editor.

Output:

Jawaban:
select studentID, FirstName, LastName, Semester1, Semester2, ABS(MarkGrowth) as MarkGrowth from students

## Fungsi Skalar Matematika - CEILING()

Fungsi CEILING()

Syntax:

SELECT CEILING(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select StudentID, FirstName, LastName, ceiling(Semester1) as semester1, ceiling(Semester2) as semester2, MarkGrowth from students

## Fungsi Skalar Matematika - FLOOR()

Fungsi FLOOR()

Syntax:

SELECT FLOOR(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select StudentID, FirstName, LastName, floor(Semester1) as semester1, floor(Semester2) as semester2, MarkGrowth from students

## Fungsi Skalar Matematika - ROUND()

Fungsi ROUND()

Syntax:

SELECT ROUND(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select StudentID, FirstName, LastName, round(Semester1,1) as semester1, round(Semester2, 0) as semester2, MarkGrowth from students

## Fungsi Skalar Matematika - SQRT( )

Fungsi SQRT()

Syntax:

SELECT SQRT(ColumnName)  
FROM TableName;

Contoh:

Tugas:
Ketiklah contoh yang diberikan pada baris di atas pada live code editor.

Output:

Jawaban:
select StudentID, FirstName, LastName, sqrt(Semester1) as semester1, Semester2, MarkGrowth from students

## Tugas Praktek

Tugas:
Gunakan fungsi MOD() untuk menghitung nilai sisa jika nilai Semester1 dibagi 2 dan fungsi EXP() untuk menghitung nilai eksponensial dari nilai MarkGrowth. Gunakan kedua fungsi tersebut dalam satu SELECT-Statement.

Jika berhasil, berikut output tabel yang diperoleh:

Jawaban:
select StudentID, FirstName, LastName, mod(Semester1,2) as semester1, Semester2, exp(MarkGrowth) from students
