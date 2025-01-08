# Uji Kesegaran Buah Anggur Menggunakan Pengolahan Citra Digital

## Deskripsi Project
Proyek ini menggunakan teknik pengolahan citra digital untuk menguji kesegaran buah anggur. Kami menggunakan citra buah anggur untuk mengekstraksi fitur-fitur seperti warna (RGB) dan nilai dari model warna HSV. Setelah itu, kami melabeli buah anggur berdasarkan nilai-nilai fitur yang diekstraksi, melatih model klasifikasi dengan menggunakan algoritma K-Nearest Neighbors (KNN), dan melakukan evaluasi untuk menentukan apakah buah anggur tersebut segar atau tidak segar.


## Struktur Direktori

```
├── dataset/
├── resized_dataset/
├── segmented_dataset/
├── PCD_Kesegaran_Buah_Anggur.ipynb
├── README.md
├── fitur_anggur.csv
├── fitur_anggur_labeled.csv
└── requirements.txt
```

## Langkah-Langkah Proyek

1. **Mengumpulkan Data**
   Kami memuat gambar anggur dari folder `dataset/` dan menyimpannya ke dalam variabel Python untuk proses lebih lanjut.

2. **Preprocessing**
   Gambar-gambar tersebut diubah ukurannya menjadi resolusi 256x256 piksel dan disimpan kembali di dalam folder `resized_dataset/`.

3. **Segmentasi**
   Setiap gambar yang telah di-resize kemudian diubah menjadi citra biner dengan menggunakan metode segmentasi berbasis threshold, dan hasilnya disimpan di folder `segmented_dataset/`.

4. **Ekstraksi Fitur**
   Fitur dari gambar yang telah di-segmentasi diekstraksi berdasarkan rata-rata nilai RGB dan HSV. Fitur ini kemudian disimpan dalam file CSV `fitur_anggur.csv`.

5. **Visualisasi**
   Data fitur yang diekstraksi divisualisasikan dalam bentuk scatter plot dan histogram untuk melihat distribusi warna dan nilai HSV.

6. **Pelabelan**
   Kami menetapkan label pada dataset berdasarkan kriteria tertentu, misalnya menggunakan rata-rata nilai R (Red) untuk menentukan apakah anggur tersebut segar atau tidak segar. Data yang telah dilabeli disimpan dalam file `fitur_anggur_labeled.csv`.

7. **Pembagian Dataset**
   Dataset dibagi menjadi data training dan data testing dengan rasio 80:20. Data training digunakan untuk melatih model K-Nearest Neighbors (KNN), sedangkan data testing digunakan untuk mengevaluasi model.

8. **Klasifikasi dengan KNN**
   Model KNN dengan K=3 dilatih menggunakan data fitur, dan kemudian dievaluasi dengan menggunakan data testing. Hasil prediksi dibandingkan dengan label aktual, dan akurasi model dihitung.

9. **Evaluasi Model**
   Akurasi model KNN dihitung, dan kami juga menampilkan laporan klasifikasi serta matriks konfusi untuk menganalisis kinerja model dalam memprediksi kesegaran buah anggur.

## Hasil Evaluasi
- **Akurasi Model**: Akurasi model KNN dengan K=3 adalah sekitar `1.0`.
- **Matriks Konfusi**: Kami menampilkan matriks konfusi untuk memvisualisasikan hasil prediksi model.

## Cara Menggunakan

1. Unduh file proyek.
2. Pastikan semua dependencies yang diperlukan sudah terinstal:
   ```
   pip install -r requirements.txt
