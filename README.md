# Slum Mapping with Big Data Geospasial

# Abstrak
Pemetaan wilayah kumuh dibutuhkan untuk mengatasi dan mengevaluasi pembangunan dan tata kota. Identifikasi wilayah kumuh konvensional dengan menggunakan survei lapangan selama ini memiliki banyak kekurangan, antara lain waktu pelaksanaan yang lama, dan pembaruan data yang lama. Penelitian ini bertujuan untuk memanfaatkan big data geospasial menggunakan data citra satelit dan analisis Point Of Interest (POI) OpenStreetMap dalam mengidentifikasi wilayah kumuh di Kota Semarang. Pengklasifikasian kawasan wilayah kumuh dilakukan dengan permodelan machine learning  menggunakan tiga algoritma Decision Tree, Random Forest, dan XG-Boost. Hasil penelitian menunjukkan model klasifikasi menggunakan fitur big data geospasial dapat mengklasifikasikan wilayah kumuh dengan akurat. Algoritma XG-Boost menunjukkan performa model terbaik dari model lainnya pada metrik evaluasi F1-Score sebesar 0,933 pada data testing. Selain itu fitur Water Treatment Distance menjadi fitur paling berpengaruh pada model klasifikasi yang memiliki hubungan positif dengan kekumuhan wilayah. Hasil pemetaan pada dashboard dari tahun 2021 – 2024 terjadi penurunan wilayah kumuh di Kota Semarang berdasarkan pemetaan pada model klasifikasi wilayah kumuh yang dihasilkan.

# Informasi Running Code
### Pengolahan Data Citra
1. Code Program mulai dari pengambilan data citra menggunakan library Earth Engine pada Python
2. File .tiff pada setiap index tersedia pada folder citra
3. Code file .ipynb akan dilakukan perhitungan zonal statistic per Administrasi RT (file .shp administrasi RT didapatkan melalui silastik.go.id), untuk batas administrasi dalam cakupan kelurahan tersedia pada folder batas_administrasi

### Pengolahan POI
1. Data POI yang telah digunakan terdapat pada folder POI
2. jalankan bagian preprocessing POI pada file .ipynb untuk mendapatkan distance dan density per administrasi

### Persiapan Permodelan
1. code program .ipynb akan dimulai dengan transformasi Yeo-Johnson untuk mengubah data mendekati distribusi normal
2. selanjutnya dilakukan spliting dataset training testing sebesar 80:20
3. penanganan imbalance dataset menggunakan cluster centroid undersampling dan Smote oversampling pada data training

### Tahap Permodelan Machine Learning
1. Dilakukan permodelan menggunakan 3 algoritma yaitu Decision Tree (DT), Random Forest (RF), dan XG-Boost (XGB)
2. dataset training akan dilakukan permodelan menggunakan dataset trining pada masing-masing aloritma
3. pemilihan parameter dilakukan menggunakan GridSearch *5-fold-Cross-Validation* pada masing-masing algoritma
4. Model dengan parameter terbaik akan dilakukan evaluasi pada data testing untuk dilakukan perbandingan antar algoritma
5. Dalam Penelitian ini XGB menjadi model terbaik

### Tahap analisis Fitur
1. Dilakukan feature importance pada model XGB
2. Dilakukan SHAP Analisis pada model XGB (hasil SHAP untuk kelas kumuh ringan dan kumuh sedang digabungkan untuk diperbandingkan dengan wilayah tidak kumuh)

### Dashboard dibuat menggunakan Tableau, dashboard hasil pemetaan wilayah kumuh Kota Semarang dapat diakses pada link berikut :
https://s.stis.ac.id/dashboard_wilayah_kumuh_kota_semarang

## Pertanyaan dan Diskusi dapat menghubungi email berikut : 222112076@stis.ac.id
