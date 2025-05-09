# Analisis Sentimen Menggunakan SVM

Proyek ini merupakan implementasi sederhana dari **Analisis Sentimen** menggunakan **Support Vector Machine (SVM)**. Tujuannya adalah untuk mengklasifikasikan teks ulasan menjadi **positif** atau **negatif** berdasarkan dataset yang disediakan. Proyek ini dibuat untuk memenuhi tugas pembelajaran analisis sentimen.

## 📚 Referensi
Proyek ini diadaptasi dan dimodifikasi dari repositori GitHub milik [jatinwarade](https://github.com/jatinwarade/Sentiment-analysis-using-SVM) yang dibuat sekitar 7 tahun lalu. Kode program telah diperbarui agar sesuai dengan versi terbaru dari pustaka Python seperti `scikit-learn` dan `TextBlob`.

## 🔧 Teknologi yang Digunakan
- Python 3.x
- scikit-learn
- TextBlob
- pandas
- numpy
- matplotlib

## 🧠 Model Machine Learning
Model klasifikasi yang digunakan adalah **Support Vector Classifier (SVC)** dari pustaka `scikit-learn`. Model ini dibungkus dalam pipeline yang terdiri dari:
- **Preprocessing Teks**: Tokenisasi dan Lematisasi menggunakan `TextBlob`
- **Ekstraksi Fitur**: CountVectorizer dan TF-IDF Transformer
- **Klasifikasi**: `sklearn.svm.SVC`

### Struktur Pipeline:
```python
Pipeline([
    ('vectorizer', CountVectorizer()),
    ('tfidf', TfidfTransformer()),
    ('classifier', SVC())
])
```

## 📝 Dataset
Dataset yang digunakan berisi teks ulasan yang sudah diberi label sebagai positif atau negatif.

Contoh:
```bash
Review: "Saya sangat suka dengan filmnya!"
Sentimen: Positif

Review: "Film ini buang-buang waktu saja."
Sentimen: Negatif
```
## ⚙️ Cara Kerja
1. Dataset dibaca dari file CSV.
2. Teks diproses menggunakan TextBlob untuk lemmatisasi.
3. Teks dikonversi menjadi fitur menggunakan CountVectorizer dan TF-IDF.
4. Data dibagi menjadi data latih dan data uji.
5. Pipeline dibangun dengan SVC dan dioptimasi menggunakan GridSearchCV.
6. Model dilatih dan dievaluasi menggunakan akurasi, confusion matrix, dan classification report.

## 📈 Evaluasi Model
Setelah pelatihan, performa model dievaluasi. Contoh hasil evaluasi:
```bash
Akurasi: 0.85

Confusion Matrix:
[[45  5]
 [ 7 43]]

Classification Report:
              precision    recall  f1-score   support
    Negatif       0.87      0.90      0.88        50
    Positif       0.90      0.86      0.88        50
     Akurasi                           0.88       100
```

## 🔄 Perubahan yang Dilakukan pada Kode Asli
- Mengganti fungsi-fungsi yang sudah deprecated.
- Menyesuaikan kode dengan versi terbaru pustaka scikit-learn dan TextBlob.
- Merapikan struktur kode dan menambahkan komentar.

## 📂 Struktur Folder
```bash
Sentiment-Analysis-SVM/
├── .ipynb_checkpoint/
│   └── SVM-checkpoint.ipynb
├── SVM.ipynb
├── Training.txt
├── requirements.txt
└── README.md
```

## 🚀 Cara Menjalankan
1. Clone repositori ini:
```bash
git clone https://github.com/jasmeinalbr/Sentiment-Analysis-SVM
cd Sentiment-Analysis-SVM
```
2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Jalankan program utama:
```bash
python SVM.ipynb
```

## 📌 Kesimpulan
Proyek ini menunjukkan pendekatan dasar namun efektif dalam melakukan analisis sentimen menggunakan SVM. Dengan memodifikasi kode lama dan menggunakan pustaka modern, proses belajar dan pengembangan menjadi lebih mudah dan relevan untuk kebutuhan saat ini.