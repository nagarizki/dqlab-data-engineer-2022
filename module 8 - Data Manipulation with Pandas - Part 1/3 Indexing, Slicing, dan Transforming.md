## Indexing - Part 2

Secara default setelah suatu dataframe dibaca dari file dengan format tertentu, index-nya merupakan single index.

Pada sub bab ini akan mencetak index dan kolom yang dimiliki oleh file "https://storage.googleapis.com/dqlab-dataset/sample_csv.csv". Untuk menentukan index dan kolom yang dimiliki oleh dataset yang telah dinyatakan sebagai sebuah dataframe pandas dapat dilakukan dengan menggunakan atribut .index dan .columns.

Untuk lebih jelasnya diberikan oleh kode yang ditampilkan berikut ini:

Jika dijalankan dengan menekan tombol maka akan menghasilkan output seperti berikut di console untuk masing-masing indeks dan kolom yang dimiliki oleh dataframe df.

Tugas praktek:

Pada code editor kamu lihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Tampilkanlah index dan kolom data teratas dari file TSV "https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv" yang telah dibaca!

Jika kode yang dituliskan telah benar dan kemudian tombol ditekan, maka hasil berikut yang akan kamu peroleh di console.

Jawaban:
import pandas as pd

# Baca file TSV sample_tsv.tsv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv", sep="\t")

# Index dari df

print("Index:", df.index)

# Column dari df

print("Columns:", df.columns)

## Indexing - Part 3

Di sub bab sebelumnya telah dibahas terkait single index, tentunya pada sub bab ini akan bahas multi index atau disebut juga dengan hierarchical indexing.

Untuk membuat multi index (hierarchical indexing) dengan pandas diperlukan kolom-kolom mana saja yang perlu disusun agar index dari dataframe menjadi sebuah hirarki yang kemudian dapat dikenali.

Pada sub bab sebelumnya telah diberikan nama-nama kolom dari dataframe yang telah dibaca, yaitu:

dengan output

Selanjutnya akan membuat multi index dengan menggunakan kolom 'order_id', 'customer_id', 'product_id', dan 'order_date' dengan menggunakan method .set_index(). Mari perhatikan contoh kode yang diberikan berikut ini:

berikut hasil tampilan dataframe df_x-nya:

Untuk melihat multi index yang telah diset dapat dilakukan dengan:

yang memberikan output:

Perlu diketahui bahwa kumpulan index dari multi index adalah list dari banyak tuples, tuples-nya merupakan kombinasi yang ada dari gabungan index-index tersebut. Dari multi index tersebut juga terdapat atribut levels yang menunjukkan urutan index, dalam case ini 'order_id' > 'customer_id' > 'product_id' > 'order_date'.

yang menghasilkan output berupa:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Tampilkanlah multi index dari file TSV "sample_tsv.tsv" yang telah dibaca berupa nama dan level index-nya.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv

Kolom yang menjadi index-nya yaitu 'order_date', 'city', dan 'customer_id'!

Jika di code editor telah dengan benar ditulis kodenya dan kemudian setelah menekan tombol , maka akan memperoleh hasil berikut di console:

Jawaban:
import pandas as pd

# Baca file TSV sample_tsv.tsv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv", sep="\t")

# Set multi index df

df_x = df.set_index(['order_date', 'city', 'customer_id'])

# Print nama dan level dari multi index

for name, level in zip(df_x.index.names, df_x.index.levels):
print(name,':',level)

## Indexing - Part 4

Terdapat beberapa cara untuk membuat index, salah satunya adalah seperti yang telah dilakukan pada sub bab sebelumnya dengan menggunakan method .set_index().

Di sub bab ini akan menggunakan assignment untuk menset index dari suatu dataframe. Untuk itu file "sample_excel.xlsx" yang digunakan. Perhatikan code berikut!

Jika dijalankan dengan mengklik tombol hasilnya adalah sebagai berikut:

Note:

Cara yang ditunjukkan oleh baris ketujuh (ke-7) pada code editor di atas hanya berlaku jika index yang di-assign tersebut memiliki panjang yang sama dengan jumlah baris dari dataframe.
Jika ingin kembalikan dataframe ke index default-nya yaitu dari 0 s/d jumlah baris data - 1, maka dapat menggunakan method .reset_index(drop=True), argument drop=True bertujuan untuk menghapus index lama.

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai.

Baca kembali file TSV "sample_tsv.tsv" hanya untuk 10 baris pertama. Set index-nya dengan menggunakan nama "Pesanan ke-i" i adalah bilangan bulat dari 1 sampai dengan jumlah baris (10 baris data).

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv

Jika berhasil dijalankan kodenya maka akan tampil hasil berikut:

Jawaban:

import pandas as pd

# Baca file sample_tsv.tsv untuk 10 baris pertama saja

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv", sep="\t", nrows=10)

# Cetak data frame awal

print("Dataframe awal:\n", df)

# Set index baru

df.index = ["Pesanan ke-" + str(i) for i in range(1, 11)]

# Cetak data frame dengan index baru

print("Dataframe dengan index baru:\n", df)

## Indexing - Part 5

Jika file yang akan dibaca melalui penggunaan library pandas dapat di-preview terlebih dahulu struktur datanya maka melalui fungsi yang ditujukan untuk membaca file dapat diset mana kolom yang akan dijadikan index.

Fitur ini telah dimiliki oleh setiap fungsi yang digunakan dalam membaca data dengan pandas, yaitu penggunaan argumen index_col pada fungsi yang dimaksud. Untuk jelasnya dapat diperhatikan pada kode berikut ini.

Dari dataset sample_csv.csv, sample_tsv.tsv, atau sample_excel.xlsx sudah tahu bahwa kolom dataset adalah 'order_id'; 'order_date'; 'customer_id'; 'city'; 'province'; 'product_id'; 'brand'; 'quantity'; and 'item_price'. Sehingga kode di atas digunakan langsung kolom 'order_date' pada saat membaca file-nya.

Jika dijalankan dengan mengklik tombol maka akan menghasilkan output berikut di console.

Terlihat bahwa kolom order_date sudah jadi index, dan tentunya jumlah kolom dataframe berkurang satu, yaitu menjadi delapan kolom.

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai.

Baca kembali file TSV "sample_tsv.tsv" dan set lah kolom "order_date" dan "order_id" sebagai index_col-nya dan cetaklah dataframe untuk delapan baris pertama.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv

Jika berhasil dijalankan kodenya maka akan tampil hasil berikut:

Jawaban:
import pandas as pd

# Baca file sample_tsv.tsv dan set lah index_col sesuai instruksi

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv", sep="\t", index_col=["order_date","order_id"])

# Cetak data frame untuk 8 data teratas

print("Dataframe:\n", df.head(8))

## Slicing - Part 1

Seperti artinya slicing adalah cara untuk melakukan filter ke dataframe/series berdasarkan kriteria tertentu dari nilai kolomnya ataupun kriteria index-nya.

Terdapat 2 cara paling terkenal untuk slicing dataframe, yaitu dengan menggunakan method .loc dan .iloc pada variabel bertipe pandas DataFrame/Series. Method .iloc ditujukan untuk proses slicing berdasarkan index berupa nilai integer tertentu. Akan tetapi akan lebih sering menggunakan dengan method .loc karena lebih fleksibel.

Mari ikuti ilustrasi berikut ini.

Dataset belum dilakukan indexing, jadi slicing berdasarkan nilai kolomnya. Untuk itu "sample_csv.csv" dibaca kembali dan dipraktikkan metode .loc[] dengan mengambil tanggal 1 Januari 2019 dari kolom order_date dan product_id nya adalah P2154 dan P2556.

Jika kode di atas dijalankan dengan menekan diperoleh:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai.

Baca kembali file TSV "sample_csv.csv" dan slice/filter-lah dataset jika customer_id adalah 18055 dan product_id-nya yaitu P0029, P0040, P0041, P0116, dan P0117.

Notes :

Dataset: https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Jika berhasil dijalankan kodenya maka akan tampil hasil berikut:

Jawaban
import pandas as pd

# Baca file sample_csv.csv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")

# Slice langsung berdasarkan kolom

df_slice = df.loc[(df["customer_id"] == 18055) &
(df["product_id"].isin(["P0029","P0040","P0041","P0116","P0117"]))
]
print("Slice langsung berdasarkan kolom:\n", df_slice)

## Slicing - Part 2

Dalam sub bab sebelumnya telah mempelajari bagaimana melakukan slicing/filtering dataset dengan menggunakan method .loc pada kolom dataset.

Sekarang, menerapkan berdasarkan index. Tentu syaratnya adalah dataset sudah dilakukan indexing terlebih dahulu melalui penerapan method .set_index

Cara 1: Gunakan method .loc seperti yang dicontohkan berikut:

Output cara 1:

Cara 2: Gunakan pd.IndexSlice sebagai varaibel untuk melakukan slicing index

Output cara 2:

Tugas praktek:

Pada code editor dapat terlihat kode-kode yang tidak lengkap. Tugas kamu adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai.

Baca kembali file TSV "sample_csv.csv" dan set terlebih dahulu indexnya yaitu order_date, order_id, dan product_id. Kemudian slice/filter-lah dataset jika order_date adalah 2019-01-01, order_id adalah 1612339 dan product_id-nya yaitu P2154 dan P2159. Gunakanlah cara pertama.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Jika berhasil dijalankan kodenya maka akan tampil hasil berikut:

Jawaban:
import pandas as pd

# Baca file sample_csv.csv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")

# Set index dari df sesuai instruksi

df = df.set_index(["order_date","order_id","product_id"])

# Slice sesuai intruksi

df_slice = df.loc[("2019-01-01",1612339,["P2154","P2159"]),:]
print("Slice df:\n", df_slice)

## Transforming - Part 1

Transform adalah ketika mengubah dataset yang ada menjadi entitas baru, dapat dilakukan dengan:

konversi dari satu data type ke data type yang lain,
transpose dataframe,
atau yang lainnya.
Hal yang biasa dilakukan pertama kali setelah data dibaca adalah mengecek tipe data di setiap kolomnya apakah sesuai dengan representasinya. Untuk itu dapat menggunakan atribut .dtypes pada dataframe yang telah kita baca tadi,

[nama_dataframe].dtypes

Untuk konversi tipe data, secara default system akan mendeteksi data yang tidak bisa di render as date type or numeric type sebagai object yang basically string. Tidak bisa di render oleh system ini karena berbagai hal, mungkin karena formatnya asing dan tidak dikenali oleh python secara umum (misal: date type data → '2019Jan01').

Data contoh tersebut tidak bisa di render karena bulannya Jan tidak bisa di translate menjadi in form of number (00-12) dan tidak ada ‘-’ di antara tahun, bulan dan harinya. Jika seluruh data pada kolom di order_date sudah tertulis dalam bentuk 'YYYY-MM-DD' maka ketika dibaca, kolom order_date sudah langsung dinyatakan bertipe data datetime.

Untuk merubah kolom date_order yang sebelumnya bertipe object menjadi kolom bertipe datetime, cara pertama yang dapat dilakukan adalah menggunakan:

pd.to_datetime(argumen)
dengan argumen adalah isi kolom dari dataframe yang akan dirubah tipe datanya, misal dalam format umum.

nama_dataframe["nama_kolom"]
Sehingga lengkapnya dapat ditulis sebagai:

nama_dataframe["nama_kolom"] = pd.to_datetime(nama_dataframe["nama_kolom"])

Tugas praktek:

Ubahlah tipe data di kolom order_date yang semula bertipe objek menjadi bertipe datetime.

Di code editor telah disediakan kode yang tidak lengkap, silakan diisi sesuai dengan instruksi yang diberikan.

Jika dengan benar dituliskan dan berhasil dijalankan maka output berikut yang akan diperoleh pada console.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Jawaban:
import pandas as pd

# Baca file sample_csv.csv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")

# Tampilkan tipe data

print("Tipe data df:\n", df.dtypes)

# Ubah tipe data kolom order_date menjadi datetime

df["order_date"] = pd.to_datetime(df["order_date"])

# Tampilkan tipe data df setelah transformasi

print("\nTipe data df setelah transformasi:\n", df.dtypes)

## Transforming - Part 2

Pada sub bab ini akan mengubah tipe data pada kolom dataframe yang telah dibaca menjadi tipe data float (kolom quantity) dan tipe kategori (kolom city).

Secara umum, untuk mengubah ke numerik dapat menggunakan pd.to_numeric(), yaitu:

nama_dataframe["nama_kolom"] = pd.to_numeric(nama_dataframe["nama_kolom"], downcast="tipe_data_baru")
Sedangkan untuk menjadi suatu kolom yang dapat dinyatakan sebagai kategori dapat menggunakan method .astype() pada dataframe, yaitu

nama_dataframe["nama_kolom"] = nama_dataframe["nama_kolom"].astype("category")

Tugas Praktek:

Ubahlah tipe data di kolom

quantity yang semula bertipe int64 menjadi bertipe float32, dan
city yang semula bertipe object menjadi bertipe category
Di code editor telah disediakan kode yang tidak lengkap, silakan diisi sesuai dengan instruksi yang diberikan.

Jika dengan benar dituliskan dan berhasil dijalankan maka output berikut yang akan kamu peroleh di console.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Jawaban:
import pandas as pd

# Baca file sample_csv.csv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")

# Tampilkan tipe data

print("Tipe data df:\n", df.dtypes)

# Ubah tipe data kolom quantity menjadi tipe data numerik float

df["quantity"] = pd.to_numeric(df["quantity"], downcast="float")

# Ubah tipe data kolom city menjadi tipe data category

df["city"] = df["city"].astype("category")

# Tampilkan tipe data df setelah transformasi

print("\nTipe data df setelah transformasi:\n", df.dtypes)

## Transforming - Part 3

Sekarang akan mempelajari teknik/cara berikutnya dalam proses transformasi suatu dataframe. Di sub bab ini akan memakai method .apply() dan .map() pada suatu dataframe.

Method .apply() digunakan untuk menerapkan suatu fungsi python (yang dibuat dengan def atau anonymous dengan lambda) pada dataframe/series atau hanya kolom tertentu dari dataframe.

Berikut ini adalah contohnya yaitu akan merubah setiap baris pada kolom brand menjadi lowercase.

Jika dijalankan maka akan menghasilkan:

Method .map() hanya dapat diterapkan pada series atau dataframe yang diakses satu kolom saja. Method ini digunakan untuk mensubstitusikan suatu nilai ke dalam tiap baris datanya.

Mari lihat contoh yang diberikan berikut ini yang mana akan ambil huruf terakhir dari brand.

Jika dijalankan maka akan menghasilkan:

Tugas praktek:

Kerjakanlah seperti yang diinstruksikan melalui code editor dan di code editor juga telah disediakan kode yang tidak lengkap, silakan diisi dengan yang seharusnya. Apa yang telah dicontohkan dapat dijadikan referensi.

Jika kodenya tidak ada yang salah dan dijalankan dengan tombol maka akan memperoleh hasil berikut di console.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Jawaban:
import pandas as pd

# Baca file sample_csv.csv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")

# Cetak 5 baris teratas kolom brand

print("Kolom brand awal:\n", df["brand"].head())

# Gunakan method apply untuk merubah isi kolom menjadi lower case

df["brand"] = df["brand"].apply(lambda x: x.lower())

# Cetak 5 baris teratas kolom brand

print("Kolom brand setelah apply:\n", df["brand"].head())

# Gunakan method map untuk mengambil kode brand yaitu karakter terakhirnya

df["brand"] = df["brand"].map(lambda x: x[-1])

# Cetak 5 baris teratas kolom brand

print("Kolom brand setelah map:\n", df["brand"].head())

## Transforming - Part 4

Di sub bab sebelumnya sudah mengetahui bahwa map hanya dapat digunakan untuk pandas series. Pada sub bab ini akan menggunakan method .applymap pada dataframe.

Untuk itu perhatikan contoh berikut:

Cara 1 dengan tanpa define function awalnya, langsung pake fungsi anonymous lambda x

Cara 2 dengan define function

Setelah dijalankan dengan menekan tombol maka diperoleh output berikut di console.

Cara 1 dan cara 2 menunjukkan bahwa keduanya menghasilkan dataframe yang sama.

Tugas Praktek:

Dengan cara yang sama seperti diatas buatlah matriks random ukuran 3 x 4 dengan seed random-nya 1234. Kemudian gunakan kedua cara seperti di atas untuk merubah seluruh isi dengan fungsi kuadrat x\**2 + 3*x + 2.

Jika kode dengan benar ditulis dan kemudian dijalankan dengan menekan tombol diperoleh output berikut:

Jawaban:
import numpy as np
import pandas as pd

# number generator, set angka seed menjadi suatu angka, bisa semua angka, supaya hasil random nya selalu sama ketika kita run

np.random.seed(1234)

# create dataframe 3 baris dan 4 kolom dengan angka random

df_tr = pd.DataFrame(np.random.rand(3,4))

# Cetak dataframe

print("Dataframe:\n", df_tr)

# Cara 1 dengan tanpa define function awalnya, langsung pake fungsi anonymous lambda x

df_tr1 = df_tr.applymap(lambda x: x\**2 + 3*x + 2)
print("\nDataframe - cara 1:\n", df_tr1)

# Cara 2 dengan define function

def qudratic_fun(x):
return x\**2 + 3*x + 2
df_tr2 = df_tr.applymap(qudratic_fun)
print("\nDataframe - cara 2:\n", df_tr2)
