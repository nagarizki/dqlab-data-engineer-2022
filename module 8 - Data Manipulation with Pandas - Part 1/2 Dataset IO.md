## Read Dataset - CSV dan TSV

CSV dan TSV pada hakikatnya adalah tipe data text dengan perbedaan terletak pada pemisah antar data dalam satu baris. Pada file CSV, antar data dalam satu baris dipisahkan oleh comma, ",". Namun, pada file TSV antar data dalam satu baris dipisahkan oleh "Tab".

Fungsi .read_csv() digunakan untuk membaca file yang value-nya dipisahkan oleh comma (default), terkadang pemisah value-nya bisa di set ‘\t’ untuk file tsv (tab separated values).

Notes :
Dataset csv : https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Dataset tsv : https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv

Membaca file CSV

Jika dijalankan akan menghasilkan output di console:

Membaca file TSV

Jika dijalankan akan menghasilkan output di console:

Tugas praktek:

Pada code editor dapat kamu lihat kode-kode yang tidak lengkap. Tugas kamu sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Tampilkanlah tiga data teratas dari kedua jenis file yang telah dibaca!

Jawaban:
import pandas as pd

# File CSV

df_csv = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")
print(df_csv.head(3)) # Menampilkan 3 data teratas

# File TSV

df_tsv = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_tsv.tsv", sep='\t')
print(df_tsv.head(3)) # Menampilkan 3 data teratas

## Read Dataset - Excel

File Excel dengan ekstensi _.xls atau _.xlsx cukup banyak digunakan dalam menyimpan data. Pandas juga memiliki fitur untuk membaca file excel.

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_excel.xlsx

Fungsi .read_excel() digunakan untuk membaca file excel menjadi dataframe pandas.

Jika dijalankan code di atas akan menghasilkan output di console seperti berikut:

Tugas praktek:

Pada code editor dapat kamu lihat kode-kode yang tidak lengkap. Tugas kamu sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Tampilkanlah empat data teratas dari file excel yang telah dibaca!

Jawaban:
import pandas as pd

# File xlsx dengan data di sheet "test"

df_excel = pd.read_excel("https://storage.googleapis.com/dqlab-dataset/sample_excel.xlsx", sheet_name="test")
print(df_excel.head(4)) # Menampilkan 4 data teratas

## Read Dataset - JSON

Method .read_json() digunakan untuk membaca URL API yang formatnya JSON dan mengubahnya menjadi dataframe pandas. Method ini dapat digunakan seperti yang dicontohkan berikut ini:

Dataset JSON: https://storage.googleapis.com/dqlab-dataset/covid2019-api-herokuapp-v2.json

Jika dengan benar dituliskan code-nya di code editor maka setelah tombol diklik kemudian akan mendapatkan hasilnya di console seperti berikut:

Tugas praktek:

Pada code editor dapat dilihat kode-kode yang tidak lengkap. Tugas sekarang adalah mengganti tanda \_ \_ \_ di code editor dengan yang sesuai seperti yang diberikan pada contoh di atas.

Tampilkanlah sepuluh data teratas dari file JSON yang telah dibaca!

Jawaban:
import pandas as pd

# File JSON

url = "https://storage.googleapis.com/dqlab-dataset/covid2019-api-herokuapp-v2.json"
df_json = pd.read_json(url)
print(df_json.head(10)) # Menampilkan 10 data teratas

## Head & Tail

Seperti yang telah dipelajari sebelumnya bahwa ada method .head yang diterapkan pada suatu variabel bertipe pandas dataframe/series.

Method .head ditujukan untuk membatasi tampilan jumlah baris teratas dari dataset. Sementara itu, method .tail ditujukan untuk membatasi jumlah baris terbawah dari dataset.

Secara umum kedua method ini memiliki bentuk

[nama_dataframe].head(n)
dan

[nama_dataframe].tail(n)
dengan n merupakan jumlah baris yang akan ditampilkan, jika tidak disebutkan n = 5 (sebagai nilai default dari n).

Tugas Praktek:

Notes :

Dataset : https://storage.googleapis.com/dqlab-dataset/sample_csv.csv

Berdasarkan file sample_csv.csv cetaklah 3 data teratas dan 3 data terbawah.

Jika berhasil maka tampilan berikut yang akan kamu peroleh di console.

Jawaban:
import pandas as pd

# Baca file sample_csv.csv

df = pd.read_csv("https://storage.googleapis.com/dqlab-dataset/sample_csv.csv")

# Tampilkan 3 data teratas

print("Tiga data teratas:\n", df.head(3))

# Tampilkan 3 data terbawah

print("Tiga data terbawah:\n", df.tail(3))
