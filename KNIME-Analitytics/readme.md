# ANALISIS DATA MENGGUNAKAN SOFTWARE KNIME

Muhammad Isa Senoaji - 05111640000078

### Daftar Isi :

1. [Business Understanding](#1-bussiness-understanding)
2. [Data Understanding](#2-data-undestanding)
3. [Data Preparation](#3-data-preparation)
4. [Modeling](#4-modeling)
5. [Evaluation](#5-evaluation)
6. [Deployment](#6-deployment)

## i. Dataset

Dataset yang digunakan adalah Women's Shoe Price yang mana menceritakan tentang harga sepatu seorang wanita ketika membeli sepatu yang berasal dari kaggle. Dataset dapat di lihat/download <a href="https://www.kaggle.com/datafiniti/womens-shoes-prices">disini</a> atau terdapat pada repositori diatas.

## 1. Bussiness Understanding

Kemungkinan yang dapat ditarik informasi dari dataset diatas antara lain :
- Markup merk
- Tren Model Sepatu Terkini
- Strategi Penetapan Harga
- Korelasikan dengan dataset model sepatu pria untuk membedakan tren


## 2. Data Undestanding

- Dataset merupakan data penjualan harga sepatu wanita pada sebuah vendor Marketplace Amazon
- Dataset terdiri dari 2 file berbentuk .csv yang mana setiap file terdiri dari 10.000 baris data dan 10.212 baris data
- Field/column terdiri dari 32 column
- Untuk penjelasan lebih detail tentang detail column dapat dilihat <a href="https://developer.datafiniti.co/docs/product-data-schema">disini</a>

## 3. Data Preparation

- Download file dataset yang tersedia pada repositori diatas, file dataset terdiri dari 2 file berekstensi .csv
- Split dataset menjadi 2 bagian, satu bagian berupa file (berupa .csv) di dalam folder yang di tentukan dan satu bagian berupa database yang sebelumnya dari sebuah file kedalam database. 
- Untuk mengimport data ke database, Saya menggunakan KNIME untuk mengimport agar langsung terbuat table serta jenis tablenya didatabase dengan model sebagai berikut :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (10).png">

*** Penjelasan : terdapat 3 node, node 1 sebagai CSV Reader untuk membaca file .csv, node 2 sebagai MySQL COnnector untuk menghubungkan ke database dan node 3 untuk DB writter sebagai penulis dari file ke database.

Adapun konfigurasi masing-masing node bisa dilihat pada gambar dibawah ini :

## 4. Modeling

Untuk memodelkan proses ETL, Saya menggunakan 2 resource yaitu file local dan data pada database. setelah itu masing-masing dibaca lalu di append menjadi satu file. ketika telah diappend, tulis / buat hasil append menjadi file dan tulis juga dalam table result didatabase. 

Berikut workflow yang dibuat :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (19).png">

konfigurasi pada node 1 :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (14).png">

konfigurasi pada node 2 :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (15).png">

konfigurasi pada node 3 :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (16).png">

konfigurasi pada node 4 :

Konfigurasi node 4 tidak diperlukan, namun yang perlu diperhatikan adalah input dari node ini adalah dari node 3 (data dari DB) dan node 4 (data dari file)

konfigurasi pada node 5 :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (17).png">

konfigurasi pada node 6 :

<img src="/KNIME-Analitytics/resource/screenshot/Screenshot (18).png">



## 5. Evaluation

Dari hasil konfigurasi diatas di harapkan dapat membuat file .csv serta menulis kedalam database bernama ``` result_append ``` dari hasil append data dari file .csv dan data dari database. untuk mengetahuinya klik kanan pada masing-masing node lalu klik execute secara beratur dari node 1 sampai node 6.

setelah dilakukan percobaan, hasilnya success dan berhasil.


## 6. Deployment

berikut hasil file .csv :



berikut hasil penulisan pada database :



