# Prediksi Tingkat Permintaan Produk E-Commerce Indonesia Menggunakan PySpark ML

Repositori ini berisi proyek tugas besar mata kuliah **Big Data dan Artificial Intelligence** dengan studi kasus **Prediksi/Klasifikasi Tingkat Permintaan Produk E-Commerce Indonesia**. Proyek ini menggunakan dataset transaksi e-commerce Indonesia periode **2024–2025** yang terdiri dari beberapa file Excel bulanan, kemudian diproses menjadi satu dataset gabungan untuk dianalisis, dilakukan preprocessing, dan dimodelkan menggunakan **PySpark Machine Learning**.

## Identitas Mahasiswa

| Keterangan    | Data                        |
| ------------- | --------------------------- |
| Nama          | Wisnubuwana Prabaswara      |
| NIM           | 1203220103                  |
| Program Studi | Informatika                 |
| Kampus        | Universitas Telkom Surabaya |

## Deskripsi Singkat Proyek

Tujuan utama proyek ini adalah membangun pipeline analisis data dan machine learning untuk mengklasifikasikan tingkat permintaan produk e-commerce. Dataset transaksi bulanan digabungkan, dibersihkan, dianalisis, kemudian digunakan untuk membangun model klasifikasi menggunakan PySpark ML.

Secara umum, tahapan proyek meliputi:

1. Pengumpulan dan penggabungan data transaksi bulanan.
2. Exploratory Data Analysis (EDA) dan visualisasi data.
3. Preprocessing dan feature engineering.
4. Modeling klasifikasi menggunakan PySpark ML.
5. Evaluasi performa model dan visualisasi hasil akhir.

## Teknologi yang Digunakan

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- PySpark
- Scikit-learn
- Jupyter Notebook

## Struktur Folder Project

Struktur folder yang disarankan adalah sebagai berikut:

```text
project-root/
│
├── datasets/
│   ├── raw/
│   │   ├── Januari 2024.xlsx
│   │   ├── Februari 2024.xlsx
│   │   └── ...
│   │
│   ├── combined/
│   │   └── indonesia_ecommerce_sales_2024_2025_combined.csv
│   │
│   └── processed/
│       └── ecommerce_demand_processed.csv
│
├── notebooks/
│   ├── 01_data_loading_and_combining.ipynb
│   ├── 02_eda_and_visualization.ipynb
│   ├── 03_preprocessing_feature_engineering.ipynb
│   ├── 04_modeling_pyspark_ml.ipynb
│   └── 05_final_results_visualization.ipynb
│
├── results/
│   ├── eda/
│   ├── modeling/
│   │   ├── model_evaluation_results.csv
│   │   ├── confusion_matrix_best_model.csv
│   │   ├── confusion_matrix_best_model_named.csv
│   │   └── feature_importance_best_model.csv
│   │
│   └── final/
│       └── class_prediction_summary.csv
│
└── README.md
```

> Catatan: Folder `datasets/raw/` digunakan untuk menyimpan file Excel bulanan asli. Folder `datasets/combined/`, `datasets/processed/`, dan `results/` akan digunakan untuk menyimpan hasil pemrosesan dan hasil eksperimen.

## Alur Notebook

### 1. `01_data_loading_and_combining.ipynb`

Notebook ini digunakan untuk membaca seluruh file Excel dataset bulanan, mengambil informasi bulan dan tahun dari nama file, mengurutkan file berdasarkan periode, kemudian menggabungkannya menjadi satu dataset utama.

Output utama dari notebook ini:

```text
datasets/combined/indonesia_ecommerce_sales_2024_2025_combined.csv
```

Tahapan utama:

- Import library.
- Inisialisasi direktori project.
- Membaca file Excel dataset.
- Mapping nama bulan.
- Mengambil bulan dan tahun dari nama file.
- Mengurutkan file berdasarkan tahun dan bulan.
- Mengecek struktur kolom setiap file.
- Menggabungkan seluruh dataset.
- Menyimpan dataset gabungan ke format CSV.
- Validasi hasil penyimpanan dataset.

### 2. `02_eda_and_visualization.ipynb`

Notebook ini digunakan untuk melakukan eksplorasi awal terhadap dataset gabungan. Proses EDA dilakukan untuk memahami struktur data, distribusi nilai, missing value, duplikasi, dan pola umum yang terdapat pada dataset.

Tahapan utama:

- Membaca dataset gabungan.
- Mengecek jumlah baris dan kolom.
- Mengecek struktur dataset.
- Mengecek missing value.
- Mengecek data duplikat.
- Menampilkan ringkasan statistik numerik.
- Melakukan visualisasi distribusi dan pola data.
- Membaca dataset menggunakan PySpark untuk eksplorasi berbasis Spark.

### 3. `03_preprocessing_feature_engineering.ipynb`

Notebook ini digunakan untuk membersihkan dataset dan membentuk fitur yang akan digunakan pada tahap modeling. Dataset yang telah digabungkan diproses agar siap digunakan dalam machine learning.

Output utama dari notebook ini:

```text
datasets/processed/ecommerce_demand_processed.csv
```

Tahapan utama:

- Membaca dataset gabungan.
- Mengecek kolom dataset.
- Mengecek status pesanan.
- Memfilter transaksi selesai.
- Membersihkan dan mengonversi kolom numerik.
- Mengisi missing value pada kolom numerik.
- Membuat fitur baru yang relevan untuk prediksi permintaan.
- Membentuk target klasifikasi tingkat permintaan.
- Menyimpan dataset hasil preprocessing.
- Validasi dataset hasil preprocessing menggunakan PySpark.

### 4. `04_modeling_pyspark_ml.ipynb`

Notebook ini merupakan tahap utama machine learning. Dataset hasil preprocessing dibaca menggunakan PySpark, kemudian digunakan untuk membangun model klasifikasi tingkat permintaan produk.

Output utama dari notebook ini:

```text
results/modeling/model_evaluation_results.csv
results/modeling/confusion_matrix_best_model.csv
results/modeling/confusion_matrix_best_model_named.csv
results/modeling/feature_importance_best_model.csv
```

Model yang digunakan:

- Logistic Regression
- Decision Tree
- Random Forest

Tahapan utama:

- Inisialisasi Spark Session.
- Membaca dataset hasil preprocessing.
- Mengecek distribusi target.
- Menentukan fitur numerik dan kategorikal.
- Membagi data menjadi data latih dan data uji.
- Membuat pipeline preprocessing menggunakan PySpark ML.
- Melatih model klasifikasi.
- Mengevaluasi model menggunakan metrik accuracy, precision, recall, dan F1-score.
- Menentukan model terbaik.
- Menyimpan hasil evaluasi model.
- Menyimpan confusion matrix model terbaik.
- Menyimpan feature importance apabila model terbaik merupakan model berbasis tree.

### 5. `05_final_results_visualization.ipynb`

Notebook ini digunakan untuk menampilkan dan memvisualisasikan hasil akhir dari proses modeling. Hasil evaluasi model yang telah disimpan pada tahap sebelumnya dibaca kembali untuk dibuat grafik perbandingan performa dan ringkasan prediksi per kelas.

Output utama dari notebook ini:

```text
results/final/class_prediction_summary.csv
```

Tahapan utama:

- Membaca hasil evaluasi model.
- Menentukan model terbaik berdasarkan metrik evaluasi.
- Membuat visualisasi perbandingan accuracy, precision, recall, dan F1-score.
- Membuat visualisasi F1-score setiap model.
- Membaca confusion matrix model terbaik.
- Membuat visualisasi confusion matrix.
- Menghitung akurasi per kelas.
- Menyimpan ringkasan hasil prediksi per kelas.

## Cara Menjalankan Project

### 1. Clone Repository

```bash
git clone https://github.com/username/nama-repository.git
cd nama-repository
```

Ganti `username` dan `nama-repository` sesuai dengan akun GitHub dan nama repository yang digunakan.

### 2. Buat Virtual Environment

Untuk Windows:

```bash
python -m venv venv
venv\Scripts\activate
```

Untuk Linux/MacOS:

```bash
python -m venv venv
source venv/bin/activate
```

### 3. Install Library yang Dibutuhkan

```bash
pip install pandas numpy matplotlib seaborn scikit-learn pyspark openpyxl jupyter
```

Jika ingin menggunakan file `requirements.txt`, buat file tersebut dengan isi berikut:

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
pyspark
openpyxl
jupyter
```

Kemudian jalankan:

```bash
pip install -r requirements.txt
```

### 4. Siapkan Dataset

Letakkan seluruh file Excel dataset bulanan pada folder berikut:

```text
datasets/raw/
```

Pastikan nama file mengandung informasi bulan dan tahun agar dapat diproses oleh notebook pertama, misalnya:

```text
Januari 2024.xlsx
Februari 2024.xlsx
Maret 2024.xlsx
...
November 2025.xlsx
```

### 5. Jalankan Jupyter Notebook

```bash
jupyter notebook
```

Kemudian jalankan notebook secara berurutan:

```text
01_data_loading_and_combining.ipynb
02_eda_and_visualization.ipynb
03_preprocessing_feature_engineering.ipynb
04_modeling_pyspark_ml.ipynb
05_final_results_visualization.ipynb
```

Urutan notebook harus diikuti karena setiap notebook menghasilkan file output yang digunakan oleh notebook berikutnya.

## Catatan Penting

- Pastikan Python dan Java sudah terpasang, karena PySpark membutuhkan Java Runtime Environment.
- Pastikan folder `datasets/raw/` berisi file Excel dataset sebelum menjalankan notebook pertama.
- Jalankan notebook dari folder `notebooks/` atau dari root project. Kode sudah menyesuaikan direktori kerja agar dapat menemukan folder dataset dan results.
- Jika terjadi error pada PySpark, periksa kembali instalasi Java dan konfigurasi environment variable `JAVA_HOME`.
- Jika file output tidak ditemukan pada notebook berikutnya, pastikan notebook sebelumnya sudah dijalankan sampai selesai.

## Hasil Akhir Project

Hasil akhir dari proyek ini adalah pipeline analisis dan klasifikasi permintaan produk e-commerce yang terdiri dari:

1. Dataset gabungan transaksi e-commerce 2024–2025.
2. Dataset hasil preprocessing dan feature engineering.
3. Model klasifikasi tingkat permintaan produk menggunakan PySpark ML.
4. Hasil evaluasi model menggunakan accuracy, precision, recall, dan F1-score.
5. Confusion matrix model terbaik.
6. Visualisasi hasil akhir dan ringkasan prediksi per kelas.

## Lisensi

Project ini dibuat untuk keperluan akademik pada mata kuliah Big Data dan Artificial Intelligence.
