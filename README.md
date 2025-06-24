# Emotion-Classification


Proyek ini berfokus pada klasifikasi emosi dari ulasan pelanggan menggunakan berbagai model *deep learning*. Tujuannya adalah untuk menganalisis data tekstual dan mengkategorikannya ke dalam keadaan emosi yang telah ditentukan, yang dapat membantu bisnis memahami sentimen pelanggan dan meningkatkan layanan. Menggunakan dataset : www.kaggle.com/competitions/emotion-classification-ai-class/data

## Deskripsi Proyek

Proyek "Klasifikasi Emosi" melibatkan serangkaian langkah untuk membangun dan mengevaluasi model *deep learning* untuk analisis sentimen pada ulasan pelanggan. Proses dimulai dengan eksplorasi data, di mana struktur *dataset* dipahami, nilai yang hilang diidentifikasi, dan distribusi emosi divisualisasikan. Selanjutnya, teks ulasan pelanggan menjalani pra-pemrosesan ekstensif, termasuk pengubahan huruf, penghapusan *stop-word*, *stemming*, serta penghapusan karakter khusus, URL, dan angka.

Setelah data siap, beberapa arsitektur *deep learning* (CNN, RNN-LSTM, dan *Transformer Encoder*) dibangun dan dilatih. Keras Tuner digunakan untuk menyetel *hyperparameter* secara otomatis guna mengoptimalkan kinerja model. Model-model ini kemudian dibandingkan berdasarkan akurasi validasinya, dan model dengan kinerja terbaik dipilih untuk membuat prediksi pada *dataset* pengujian dan menghasilkan berkas *submission*.

## *Tools* dan Pustaka yang Digunakan

Proyek ini memanfaatkan Python dan beberapa pustaka utama:

* **Manipulasi dan Analisis Data**: `pandas` dan `numpy`.
* **Visualisasi Data**: `seaborn` dan `matplotlib.pyplot`.
* **Pra-pemrosesan Teks**: `re` untuk ekspresi reguler, dan `Sastrawi` untuk *stemming* dan penghapusan *stop-word* bahasa Indonesia.
* **Pembelajaran Mesin dan *Deep Learning***:
    * `scikit-learn`: Untuk pembagian data (`train_test_split`), pengkodean label (`LabelEncoder`), dan evaluasi metrik (`accuracy_score`).
    * `TensorFlow` / `Keras`: Digunakan untuk tokenisasi teks (`Tokenizer`, `pad_sequences`), pembangunan model sekuensial (`Sequential`), *layer* jaringan saraf (seperti `Embedding`, `Conv1D`, `GlobalMaxPooling1D`, `LSTM`, `MultiHeadAttention`, `Dense`, `Dropout`, `LayerNormalization`), *callback* (`EarlyStopping`), dan *optimizer* (`Adam`).
    * `keras-tuner`: Untuk penyetelan *hyperparameter* otomatis.

## Hasil Proyek

Proyek ini berhasil melatih dan mengevaluasi tiga jenis model *deep learning* untuk klasifikasi emosi: **CNN (Convolutional Neural Network)**, **RNN-LSTM (Recurrent Neural Network - Long Short-Term Memory)**, dan **Transformer Encoder**.

Dari hasil pelatihan dan penyetelan *hyperparameter* menggunakan Keras Tuner, **model Transformer menunjukkan akurasi validasi terbaik** di antara ketiganya. Akurasi validasi adalah metrik kunci yang menunjukkan seberapa baik model dapat menggeneralisasi pada data yang belum pernah dilihat sebelumnya.

Secara spesifik:
* **Model CNN:** Mencapai akurasi validasi sekitar **0.5706**.
* **Model RNN-LSTM:** Menunjukkan akurasi validasi yang lebih rendah, sekitar **0.3345**.
* **Model Transformer Encoder:** Mencapai akurasi validasi sekitar **0.6076**.

Keunggulan model *Transformer* kemungkinan besar berasal dari mekanisme *Multi-Head Attention* yang mampu menangkap dependensi kontekstual yang lebih kompleks di seluruh ulasan, bahkan untuk kata-kata yang berjauhan.

Berdasarkan hasil ini, **model Transformer Encoder dipilih sebagai model terbaik** untuk membuat prediksi akhir pada *dataset* pengujian (`data_test.csv`), dengan contoh prediksi awal menunjukkan label emosi seperti 'Fear', 'Love', dan 'Happy'.

