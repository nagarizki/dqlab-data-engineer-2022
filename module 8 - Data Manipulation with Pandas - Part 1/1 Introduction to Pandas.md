## Memanggil Library Pandas

Pandas adalah library python open source yang biasanya digunakan untuk kebutuhan data analisis. Pandas membuat Python supaya dapat bekerja dengan data yang berbentuk tabular seperti spreadsheet dengan cara pemuatan data yang cepat, manipulasi data, menggabungkan data, serta ada berbagai fungsi yang lain.

Pertama-tama, harus di import dulu Pandas library di Python script yang telah tersedia.

biasanya ketika menggunakan library Pandas, library Numpy juga di-import, sehingga menjadi:

Tugas praktek:

Pada code editor dapat terlihat kode-kode yang tidak lengkap. Tugasnya sekarang mengimpor library pandas dan juga library numpy dengan mengisi \_ \_ \_ pada masing-masing baris.

Jawaban:
import pandas as pd
import numpy as np

## DataFrame & Series

Di Pandas terdapat 2 kelas data baru yang digunakan sebagai struktur dari spreadsheet:

Series: satu kolom bagian dari tabel dataframe yang merupakan 1 dimensional numpy array sebagai basis datanya, terdiri dari 1 tipe data (integer, string, float, dll).
DataFrame: gabungan dari Series, berbentuk rectangular data yang merupakan tabel spreadsheet itu sendiri (karena dibentuk dari banyak Series, tiap Series biasanya punya 1 tipe data, yang artinya 1 dataframe bisa memiliki banyak tipe data).

Contoh:

Series

DataFrame

Tugas praktek:

Pada code editor terlihat kode-kode yang tidak lengkap. Tugasnya sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd

# Series

number_list = pd.Series([1,2,3,4,5,6])
print("Series:")
print(number_list)

# DataFrame

matrix = [[1,2,3],
          ['a','b','c'],
          [3,4,5],
          ['d',4,6]]
matrix_list = pd.DataFrame(matrix)
print("DataFrame:")
print(matrix_list)

## Atribut DataFrame & Series - Part 1

Info: Theory dan Predefined code telah diperbarui pada tanggal 12 Mei 2022, pastikan kode yang telah ditulis disesuaikan kembali.
Dataframe dan Series memiliki sangat banyak atribut yang digunakan untuk transformasi data, tetapi ada beberapa attribute yang sering dipakai. Di sini series number_list dan dataframe matrix_list pada subbab sebelumnya digunakan kembali.

Tampilan output di console untuk masing-masing penggunaan attribute berikut merupakan hasil setelah menuliskan seluruh kode di code editor dan kemudian mengklik tombol .

1. Method .info()

Method .info() digunakan untuk mengecek kolom apa yang membentuk dataframe itu, data types, berapa yang non null, dll. Method ini tidak dapat digunakan pada series, hanya pada dataframe saja.

Output di console untuk penggunaan method .info() ini adalah:

2. Attribute .shape

Attribute .shape digunakan untuk mengetahui berapa baris dan kolom, hasilnya dalam format tuple (baris, kolom).

Output di console untuk penggunaan attribute .shape ini adalah:

3. Attribute .dtypes

Attribute .dtypes digunakan untuk mengetahui tipe data di tiap kolom. Tipe data object: kombinasi untuk berbagai tipe data (number & text, etc).

Output di console untuk penggunaan attribute .dtypes ini adalah:

4. Method .astype(nama_tipe_data)

Method .astype(nama_tipe_data) untuk convert tipe data berdasarkan tipe data seperti: float, int, str, numpy.float, numpy.int ataupun numpy.datetime.

Output di console untuk penggunaan method .astype() ini adalah:

Tugas praktek:

Pada code editor dapat terlihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd

# Series

number_list = pd.Series([1,2,3,4,5,6])

# DataFrame

matrix_list = pd.DataFrame([[1,2,3],
				            ['a','b','c'],
				            [3,4,5],
				            ['d',4,6]])

# [1] method .info()

print("[1] method .info()")
print(matrix_list.info())

# [2] attribute .shape

print("\n[2] attribute .shape")
print(" Shape dari number_list:", number_list.shape)
print(" Shape dari matrix_list:", matrix_list.shape)

# [3] attribute .dtypes

print("\n[3] attribute .dtypes")
print(" Tipe data number_list:", number_list.dtypes)
print(" Tipe data matrix_list:", matrix_list.dtypes)

# [4] attribute .astype()

print("\n[4] method .astype()")
print(" Konversi number_list ke str:", number_list.astype("str"))
print(" Konversi matrix_list ke str:", matrix_list.astype("str"))

## Atribut DataFrame & Series - Part 2

Dataframe dan Series memiliki sangat banyak atribut yang digunakan untuk transformasi data, tetapi ada beberapa attribute yang sering dipakai. Di sini series number_list dan data frame matrix_list digunakan kembali.

Tampilan output di console untuk masing-masing penggunaan attribute berikut merupakan hasil setelah menuliskan seluruh kode di code editor dan kemudian mengklik tombol .

5. Attribute .copy()

Attribute .copy() digunakan melakukan duplikat, untuk disimpan di variable yang berbeda mungkin supaya tidak loading data lagi.

Output di console untuk penggunaan attribute .copy() ini adalah:

6. Attribute .to_list()

Attribute .to_list() digunakan untuk mengubah series menjadi list dan tidak dapat digunakan untuk dataframe.

Output di console untuk penggunaan attribute .to_list() ini adalah:

7. Attribute .unique()

Attribute .unique() digunakan menghasilkan nilai unik dari suatu kolom, hasilnya dalam bentuk numpy array. Attribute ini hanya digunakan pada series saja.

Output di console untuk penggunaan attribute .unique() ini adalah:

Tugas praktek:

Pada code editor dapat terlihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd

# Series

number_list = pd.Series([1,2,3,4,5,6])

# DataFrame

matrix_list = pd.DataFrame([[1,2,3],
				            ['a','b','c'],
				            [3,4,5],
				            ['d',4,6]])

# [5] attribute .copy()

print("[5] attribute .copy()")
num_list = number_list.copy()
print(" Copy number_list ke num_list:", num_list)
mtr_list = matrix_list.copy()
print(" Copy matrix_list ke mtr_list:", mtr_list)

# [6] attribute .to_list()

print("[6] attribute .to_list()")
print(number_list.to_list())

# [7] attribute .unique()

print("[7] attribute .unique()")
print(number_list.unique())

## Atribut DataFrame & Series - Part 3

Dataframe dan Series memiliki sangat banyak atribut yang digunakan untuk transformasi data, tetapi ada beberapa attribute yang sering dipakai. Di sini series number_list dan data frame matrix_list pada subbab sebelumnya digunakan kembali.

Tampilan output di console untuk masing-masing penggunaan attribute berikut merupakan hasil setelah menuliskan seluruh kode di code editor dan kemudian mengklik tombol .

8. Attribute .index

Attribute .index digunakan untuk mencari index/key dari Series atau Dataframe.

Output di console untuk penggunaan attribute .index ini adalah:

9. Attribute .columns

Attribute .columns digunakan untuk mengetahui apa saja kolom yang tersedia di dataframe tersebut (hanya digunakan untuk dataframe saja).

Output di console untuk penggunaan attribute .columns ini adalah:

10. Attribute .loc

Attribute .loc digunakan slice dataframe atau series berdasarkan nama kolom dan/atau nama index.

Output di console untuk penggunaan attribute .loc[] ini adalah:

11. Attribute .iloc

Attribute .iloc digunakan untuk slice dataframe atau series berdasarkan index kolom dan/atau index.

Output di console untuk penggunaan attribute .iloc[] ini adalah:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd

# Series

number_list = pd.Series([1,2,3,4,5,6])

# DataFrame

matrix_list = pd.DataFrame([[1,2,3],
				            ['a','b','c'],
				            [3,4,5],
				            ['d',4,6]])

# [8] attribute .index

print("[8] attribute .index")
print(" Index number_list:", number_list.index)
print(" Index matrix_list:", matrix_list.index)

# [9] attribute .columns

print("[9] attribute .columns")
print(" Column matrix_list:", matrix_list.columns)

# [10] attribute .loc

print("[10] attribute .loc")
print(" .loc[0:1] pada number_list:", number_list.loc[0:1])
print(" .loc[0:1] pada matrix_list:", matrix_list.loc[0:1])

# [11] attribute .iloc

print("[11] attribute .iloc")
print(" iloc[0:1] pada number_list:", number_list.iloc[0:1])
print(" iloc[0:1] pada matrix_list:", matrix_list.iloc[0:1])

## Creating Series & Dataframe from List

Untuk membuat Series atau Dataframe bisa dari berbagai macam tipe data container/mapping di python, seperti list dan dictionary, maupun dari numpy array.

Pada sub bagian ini, kamu akan membuat Series dan Dataframe yang bersumber dari list. Sekadar meninjau bahwa list merupakan sebuah kumpulan data berbagai macam tipe data yang mutable (dapat diganti).

Series

Contoh membuat series dari list:

Output di console:

DataFrame

Contoh membuat dataframe dari list of list:

Output di console:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd

# Creating series from list

ex_list = ['a',1,3,5,'c','d']
ex_series = pd.Series(ex_list)
print(ex_series)

# Creating dataframe from list of list

ex_list_of_list = [[1, 'a', 'b', 'c'],
                   [2.5, 'd', 'e', 'f'],
		           [5, 'g', 'h', 'i'],
		           [7.5, 'j', 10.5, 'l']]
index = ['dq', 'lab', 'kar', 'lan']
cols = ['float', 'char', 'obj', 'char']
ex_df = pd.DataFrame(ex_list_of_list, index=index, columns=cols)
print(ex_df)

## Creating Series & Dataframe from Dictionary

Untuk membuat Series atau Dataframe bisa dari berbagai macam tipe data container/mapping di python, seperti list dan dictionary, maupun dari numpy array.

Pada sub bagian ini, akan membuat Series dan Dataframe yang bersumber dari dictionary. Sekadar meninjau bahwa, dictionary merupakan kumpulan data yang strukturnya terdiri dari key dan value.

Series

Contoh membuat series dari dictionary:

Output di console:

DataFrame

Contoh membuat dataframe dari dict dengan setiap pasangan key dan value-nya berisi list yang sama panjangnya:

Output di console:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd

# Creating series from dictionary

dict_series = {'1':'a',
'2':'b',
'3':'c'}
ex_series = pd.Series(dict_series)
print(ex_series)

# Creating dataframe from dictionary

df_series = {'1':['a','b','c'],
'2':['b','c','d'],
'4':[2,3,'z']}
ex_df = pd.DataFrame(df_series)
print(ex_df)

## Creating Series & Dataframe from Numpy Array

Untuk membuat Series atau Dataframe bisa dari berbagai macam tipe data container/mapping di python, seperti list dan dictionary, maupun dari numpy array.

Pada sub bagian ini, akan membuat Series dan Dataframe yang bersumber dari numpy array. Sekadar meninjau bahwa, numpy array kumpulan data yang terdiri atas berbagai macam tipe data, mutable, tapi dibungkus dalam array oleh library Numpy.

Series

Contoh membuat series dari numpy array 1D:

Output:

DataFrame

Contoh membuat dataframe dari numpy array 2D:

Output:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Jawaban:
import pandas as pd
import numpy as np

# Creating series from numpy array (1D)

arr_series = np.array([1,2,3,4,5,6,6,7])
ex_series = pd.Series(arr_series)
print(ex_series)

# Creating dataframe from numpy array (2D)

arr_df = np.array([[1 ,2 ,3 ,5],
                   [5 ,6 ,7 ,8],
                   ['a','b','c',10]])
ex_df = pd.DataFrame(arr_df)
print(ex_df)
