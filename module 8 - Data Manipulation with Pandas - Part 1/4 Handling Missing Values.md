## Inspeksi Missing Value

Value yang hilang/tidak lengkap dari dataframe akan membuat analisis atau model prediksi yang dibuat menjadi tidak akurat dan mengakibatkan keputusan salah yang diambil. Terdapat beberapa cara untuk mengatasi data yang hilang/tidak lengkap tersebut.

Data COVID-19 yang akan digunakan ini diambil dari google big query, tetapi sudah disediakan datasetnya dalam format csv dengan nama https://storage.googleapis.com/dqlab-dataset/datacovid19.csv. Ini adalah studi kasus untuk meng-handle missing value. Bagaimanakah langkah-langkahnya?

Di pandas data yang hilang umumnya direpresentasikan dengan NaN.

Langkah pertama, harus tahu kolom mana yang terdapat data hilang dan berapa banyak dengan cara:

Cara 1: menerapkan method .info() pada dataframe yang dapat diikuti dari kode berikut ini:

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/datacovid19.csv

Output baris kode kelima:

Cara 2: mengetahui berapa banyak nilai hilang dari tiap kolom di dataset tersebut dengan menerapkan chaining method pada dataframe yaitu .isna().sum(). Method .isna() digunakan untuk mengecek berapa data yang bernilai NaN dan .sum() menjumlahkannya secara default untuk masing-masing kolom dataframe.

Perhatikanlah kode berikut!

Output untuk baris kode ketujuh dan kedelapan:

Seperti kedua output di atas, artinya ada beberapa kolom yang ada null sebagian dan ada yang nilainya null semua untuk kolomnya.

Tugas Praktek:

Ketikkanlah kembali statement seperti yang ditunjukkan dalam kedua cara untuk mendeteksi missing value pada dataframe dengan mengisi tanda \_ \_ \_ di code editor.

Jika dijalankan dengan menekan tombol maka akan diperoleh kedua output di atas di bagian console.

Jawaban:
import pandas as pd

# Baca file "https://storage.googleapis.com/dqlab-dataset/datacovid19.csv"

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/datacovid19.csv")

# Cetak info dari df

print(df.info())

# Cetak jumlah missing value di setiap kolom

mv = df.isna().sum()
print("\nJumlah missing value per kolom:\n", mv)

## Treatment untuk Missing Value - Part 2

Sekarang dapat menerapkan dua aksi yaitu

Membiarkannya saja
Menghapus kolom

Treatment pertama (membiarkannya saja) seperti pada kolom confirmed, death, dan recovered. Akan tetapi jika tidak ada yang terkonfirmasi, meninggal dan sembuh sebenarnya dapat menukar value ini dengan angka nol. Meskipun ini lebih make sense dalam representasi datanya, tetapi untuk sub bab ini ketiga kolom tersebut diasumsikan dibiarkan memiliki nilai missing value.

Treatment kedua yaitu dengan menghapus kolom, yang mana ini digunakan jika seluruh kolom dari dataset yang dipunyai semua barisnya adalah missing value. Untuk itu dapat menerapkan method .dropna() pada dataframe, bagaimana caranya?

nama_dataframe.dropna(axis=1, how="all")
Pada method .dropna() ada dua keyword argumen yang harus diisikan yaitu axis dan how. Keyword axis digunakan untuk menentukan arah dataframe yang akan dibuang angka 1 untuk menyatakan kolom (column-based) atau dapat ditulis dalam string "column". Jika digunakan angka 0 berarti itu dalam searah index (row-based) atau dapat ditulis dalam string "index".

Sementara, keyword how digunakan untuk bagaimana cara membuangnya. Opsi yang dapat diterimanya (dalam string) adalah

"all" artinya jika seluruh data di satu/beberapa kolom atau di satu/beberapa baris adalah missing value.
"any" artinya jika memiliki 1 saja data yang hilang maka buanglah baris/kolom tersebut.

Tugas Praktek:

Cetaklah ukuran awal dari dataframe dengan atribut .shape pada dataframe yang telah dibaca.
Buanglah kolom jika memiliki seluruh data adalah missing value, kemudian cetaklah ukurannya.
Dari dataframe hasil langkah kedua buanglah baris-baris yang setidaknya memiliki satu saja missing value, dan cetak kembali ukurannya.
Jika berhasil akan ditampilkan output-nya sebagai berikut:

Notes:

Dataset: https://storage.googleapis.com/dqlab-dataset/datacovid19.csv

Jawaban:
import pandas as pd

# Baca file "https://storage.googleapis.com/dqlab-dataset/datacovid19.csv"

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/datacovid19.csv")

# Cetak ukuran awal dataframe

print("Ukuran awal df: %d baris, %d kolom." % df.shape)

# Drop kolom yang seluruhnya missing value dan cetak ukurannya

df = df.dropna(axis=1, how="all")
print("Ukuran df setelah buang kolom dengan seluruh data missing: %d baris, %d kolom." % df.shape)

# Drop baris jika ada satu saja data yang missing dan cetak ukurannya

df = df.dropna(axis=0, how="any")
print("Ukuran df setelah dibuang baris yang memiliki sekurangnya 1 missing value: %d baris, %d kolom." % df.shape)

## Treatment untuk Missing Value - Part 3

Sekarang, akan melakukan treatment ketiga untuk melakukan handle missing value pada dataframe. Treatment ini dilakukan dengan cara mengisi missing value dengan nilai lain, yang dapat berupa :

nilai statistik seperti mean atau median
interpolasi data
text tertentu

Akan mulai pada kolom yang missing yang tipe datanya adalah berupa object. Kolom tersebut adalah province_state, karena tidak tahu secara persis province_state mana yang dimaksud, bisa menempatkan string "unknown" sebagai substitusi missing value. Meskipun keduanya berarti sama-sama tidak tahu tetapi berbeda dalam representasi datanya.

Untuk melakukan hal demikian dapat menggunakan method .fillna() pada kolom dataframe yang dimaksud. Perhatikan kode berikut!

Jika dijalankan akan menghasilkan output berikut di console:

Terlihat bahwa unique value di kolom "province_state" yang semula ada nan telah berubah menjadi "unknown".

Tugas Praktek:

Lakukanlah dengan cara yang sama dengan yang telah dicontohkan di atas, tetapi isilah missing value dengan string "unknown_province_state".

Jika dituliskan dengan benar dan dijalankan dengan maka output di console berikut akan diperoleh.

Notes :

Dataset: https://storage.googleapis.com/dqlab-dataset/datacovid19.csv

Jawaban:
import pandas as pd

# Baca file "https://storage.googleapis.com/dqlab-dataset/datacovid19.csv"

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/datacovid19.csv")

# Cetak unique value pada kolom province_state

print("Unique value awal:\n", df["province_state"].unique())

# Ganti missing value dengan string "unknown_province_state"

df["province_state"] = df["province_state"].fillna("unknown_province_state")

# Cetak kembali unique value pada kolom province_state

print("Unique value setelah fillna:\n", df["province_state"].unique())

## Treatment untuk Missing Value - Part 4

Masih melanjutkan bagaimana melakukan handle missing value tentunya dengan jalan mengganti missing value dengan nilai lainnya. Pada bab sebelumnya telah mengganti kolom bertipe objek dengan sesuatu string/teks.

Dalam sub bab ini akan mengganti missing value dengan nilai statistik kolom bersangkutan, baik median atau mean (nilai rata-rata). Misalnya akan menggunakan kolom active. Dengan mengabaikan terlebih dahulu sebaran berdasarkan negara (univariate), jika mengisi dengan nilai rata-rata maka harus melihat terlebih dahulu data apakah memiliki outliers atau tidak. Jika ada outliers dari data maka menggunakan nilai tengah (median) data adalah cara yang lebih safe.

Untuk itu diputuskan dengan mengecek nilai median dan nilai mean kolom active juga nilai min dan max-nya. Jika data pada kolom active terdistribusi normal maka nilai mean dan median akan hampir sama.

Terlihat data memiliki distribusi yang skewness, karena nilai mean dan median yang cukup jauh serta range data yang cukup lebar. Di sini pada kolom active data memiliki outliers. Jadi akan mengisi missing value dengan median.

Jika dijalankan dengan menekan tombol diperoleh output:

Tugas Praktek:

Carilah perbedaan nilai mean dan median kolom active untuk kondisi sebelum dan setelah missing value-nya diisi masing-masingnya dengan median dan mean.

Jika berjalan lancar maka akan diperoleh hasil seperti berikut ini di console:

Notes:

Dataset: https://storage.googleapis.com/dqlab-dataset/datacovid19.csv

Jawaban:
import pandas as pd

# Baca file "https://storage.googleapis.com/dqlab-dataset/datacovid19.csv"

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/datacovid19.csv")

# Cetak nilai mean dan median awal

print("Awal: mean = %f, median = %f." % (df["active"].mean(), df["active"].median()))

# Isi missing value kolom active dengan median

df_median = df["active"].fillna(df["active"].median())

# Cetak nilai mean dan median awal setelah diisi dengan median

print("Fillna median: mean = %f, median = %f." % (df_median.mean(), df_median.median()))

# Isi missing value kolom active dengan mean

df_mean = df["active"].fillna(df["active"].mean())

# Cetak nilai mean dan median awal setelah diisi dengan mean

print("Fillna mean: mean = %f, median = %f." % (df_mean.mean(), df_mean.median()))

## Treatment untuk Missing Value - Part 5

Di bagian ini akan menggunakan teknik interpolasi dalam mengisi nilai missing value pada suatu dataset.

Data yang menggunakan interpolasi untuk mengisi data yang hilang adalah time series data, yang secara default akan diisi dengan interpolasi linear.

Perhatikan kode berikut:

Jika dijalankan akan menghasilkan:

Tugas praktek:

Kerjakan kembali seperti contoh kode di atas dengan hasil output seperti yang ditujukkan berikut ini:

Jawaban:
import numpy as np
import pandas as pd

# Data

ts = pd.Series({
"2020-01-01":9,
"2020-01-02":np.nan,
"2020-01-05":np.nan,
"2020-01-07":24,
"2020-01-10":np.nan,
"2020-01-12":np.nan,
"2020-01-15":33,
"2020-01-17":np.nan,
"2020-01-16":40,
"2020-01-20":45,
"2020-01-22":52,
"2020-01-25":75,
"2020-01-28":np.nan,
"2020-01-30":np.nan
})

# Isi missing value menggunakan interpolasi linier

ts = ts.interpolate()

# Cetak time series setelah interpolasi linier

print("Setelah diisi missing valuenya:\n", ts)
