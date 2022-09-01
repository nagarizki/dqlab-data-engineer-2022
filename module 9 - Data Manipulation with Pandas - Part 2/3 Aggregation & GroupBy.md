## Review Inspeksi Data

import pandas as pd

# Load data global_air_quality.csv

global_air_quality = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')
print('Lima data teratas:\n', global_air_quality.head())

# Melakukan pengecekan terhadap data

print('Info global_air_quality:\n', global_air_quality.info())

# Melakukan count tanpa groupby

print('Count tanpa groupby:\n', global_air_quality.count())

# Melakukan count dengan groupby

gaq_groupby_count = global_air_quality.groupby('source_name').count()
print('Count dengan groupby (5 data teratas):\n', gaq_groupby_count.head())

## Groupby dan Aggregasi dengan Fungsi Statistik Dasar - Part 1

import pandas as pd

# Load data global_air_quality.csv

gaq = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')

# Create variabel pollutant 

pollutant = gaq[['country','city','pollutant','value']].pivot_table(index=['country','city'],columns='pollutant').fillna(0)
print('Data pollutant (5 teratas):\n', pollutant.head())

# [1] Group berdasarkan country dan terapkan aggregasi mean

pollutant_mean = pollutant.groupby('country').mean()
print('Rata-rata pollutant (5 teratas):\n', pollutant_mean.head())

# [2] Group berdasarkan country dan terapkan aggregasi std

pollutant_std = pollutant.groupby('country').std().fillna(0)
print('Standar deviasi pollutant (5 teratas):\n', pollutant_std.head())

## Groupby dan Aggregasi dengan Fungsi Statistik Dasar - Part 2

import pandas as pd

# Load data https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv

gaq = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')

# Create variabel pollutant 

pollutant = gaq[['country','city','pollutant','value']].pivot_table(index=['country','city'],columns='pollutant').fillna(0)
print('Data pollutant (5 teratas):\n', pollutant.head())

# [3] Group berdasarkan country dan terapkan aggregasi sum

pollutant_sum = pollutant.groupby('country').sum()
print('Total pollutant (5 teratas):\n', pollutant_sum.head())

# [4] Group berdasarkan country dan terapkan aggregasi nunique

pollutant_nunique = pollutant.groupby('country').nunique()
print('Jumlah unique value pollutant (5 teratas):\n', pollutant_nunique.head())

## Groupby dan Aggregasi dengan Fungsi Statistik Dasar - Part 3

import pandas as pd

# Load data https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv

gaq = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')

# Create variabel pollutant 

pollutant = gaq[['country','city','pollutant','value']].pivot_table(index=['country','city'],columns='pollutant').fillna(0)
print('Data pollutant (5 teratas):\n', pollutant.head())

# Group berdasarkan country dan terapkan aggregasi first

pollutant_first = pollutant.groupby('country').first()
print('Item pertama pollutant (5 teratas):\n', pollutant_first.head())

# Group berdasarkan country dan terapkan aggregasi last

pollutant_last = pollutant.groupby('country').last()
print('Item terakhir pollutant (5 teratas):\n', pollutant_last.head())

## Groupby dengan Multiple Aggregations

import pandas as pd

# Load data https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv

gaq = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')

# Create variabel pollutant 

pollutant = gaq[['country','city','pollutant','value']].pivot_table(index=['country','city'],columns='pollutant').fillna(0)
print('Data pollutant (5 teratas):\n', pollutant.head())

# Group berdasarkan country dan terapkan aggregasi: min, median, mean, max

multiagg = pollutant.groupby('country').agg(['min','median','mean','max'])
print('Multiple aggregations (5 teratas):\n', multiagg.head())

## Groupby dengan Custom Aggregations

import pandas as pd

# Load data https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv

gaq = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')

# Create variabel pollutant 

pollutant = gaq[['country','city','pollutant','value']].pivot_table(index=['country','city'],columns='pollutant').fillna(0)

# Create sebuah function: iqr

def iqr(series):
Q1 = series.quantile(0.25)
Q3 = series.quantile(0.75)
return Q3-Q1

# Group berdasarkan country dan terapkan aggregasi dari function: iqr

custom_agg = pollutant.groupby('country').agg(iqr)
print('Custom aggregation (5 teratas):\n', custom_agg.head())

## Groupby dengan Custom Aggregations by dict

import pandas as pd

# Load data https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv

gaq = pd.read_csv('https://storage.googleapis.com/dqlab-dataset/LO4/global_air_quality_4000rows.csv')

# Create variabel pollutant 

pollutant = gaq[['country','city','pollutant','value']].pivot_table(index=['country','city'],columns='pollutant').fillna(0)
print('Data pollutant (5 teratas):\n', pollutant.head())

# Function IQR

def iqr(series):
return series.quantile(0.75) - series.quantile(0.25)

# Create custom aggregation using dict

custom_agg_dict = pollutant['value']['pm10', 'pm25', 'so2']].groupby('country').agg({
'pm10':'median',
'pm25':iqr,
'so2':iqr
})
print('\nCetak 5 data teratas custom_agg_dict:\n', custom_agg_dict.head())
