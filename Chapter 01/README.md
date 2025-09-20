Fondasi TensorFlow 2 dan Deep Learning
Bagian 1 buku ini Merupakan fondasi penting yang berfokus pada pengenalan dasar-dasar TensorFlow sebagai kerangka kerja dan konsep-konsep inti dari deep learning. 
Tujuannya adalah untuk membekali pembaca dengan pemahaman teoretis dan praktis yang diperlukan sebelum melangkah ke aplikasi yang lebih kompleks di bagian-bagian selanjutnya.

Mencakup:
- Pengantar ke TensorFlow dan peran perangkat keras (CPU, GPU, TPU).
- Penjelasan mendalam tentang building blocks dasar TensorFlow.
- Cara menggunakan API Keras untuk membangun model dengan cepat.
- Membangun pipeline data yang efisien.
- Pengenalan pada arsitektur jaringan saraf dasar (FCN, CNN, RNN) dan konsep model-model modern seperti Transformer.

Penjelasan Teoretis dan Konsep Utama Tiap Bab
1. Pengantar ke TensorFlow
Bab ini memperkenalkan TensorFlow sebagai kerangka kerja machine learning sumber terbuka yang dibuat oleh Google. Konsep utamanya adalah grafik komputasi (atau dataflow graphs), di mana semua operasi dan variabel diwakili sebagai node dalam grafik. TensorFlow dirancang untuk menjalankan komputasi ini pada berbagai jenis perangkat keras (CPU, GPU, TPU) secara efisien, terutama untuk tugas-tugas yang membutuhkan komputasi berat seperti pelatihan jaringan saraf dalam.
CPU: Cocok untuk komputasi serial dan kontrol alur program.
GPU: Dirancang untuk komputasi paralel masif, membuatnya sangat efektif untuk matriks dan operasi tensor yang merupakan inti dari deep learning.
TPU: Chip khusus yang dioptimalkan oleh Google untuk workload TensorFlow, menawarkan kecepatan luar biasa untuk pelatihan model berskala sangat besar.

2. Dasar-dasar TensorFlow
Bab adalah inti yang menjelaskan blok-blok bangunan dasar yang Anda gunakan setiap hari saat bekerja dengan TensorFlow.
tf.Tensor: Ini adalah unit data utama di TensorFlow. Sebuah tensor adalah generalisasi dari vektor (1-D) dan matriks (2-D) ke dimensi yang lebih tinggi. Tensor tidak dapat diubah (immutable), yang berarti setelah dibuat, isinya tidak bisa diubah.
tf.Variable: Ini adalah kelas khusus untuk data yang dapat diubah (mutable), seperti bobot dan bias dalam jaringan saraf. Nilai sebuah tf.Variable dapat diperbarui selama proses pelatihan. Perbedaan antara tf.Tensor dan tf.Variable sangat penting: tf.Tensor mewakili data yang mengalir melalui grafik komputasi, sedangkan tf.Variable mewakili parameter model yang dioptimalkan oleh algoritma.
tf.Operation: Semua komputasi yang Anda lakukan pada tensor di TensorFlow (misalnya, penjumlahan, perkalian matriks) direpresentasikan sebagai operasi.

3. Menggunakan Keras untuk Membangun Model
Keras adalah API tingkat tinggi yang sangat mudah digunakan dan terintegrasi penuh ke dalam TensorFlow. Ini menyederhanakan proses pembangunan model deep learning.
Model Sequential: Model paling sederhana, yang digunakan untuk tumpukan lapisan linear (satu lapisan input, beberapa lapisan tersembunyi, dan satu lapisan output). Ini cocok untuk model yang memiliki satu input dan satu output tanpa percabangan.
Model Functional: API yang lebih fleksibel yang memungkinkan Anda membuat model dengan topologi yang lebih kompleks, seperti model dengan banyak input atau output, atau model yang memiliki jalur data non-linear.
Model Sub-classing: Metode paling fleksibel, di mana Anda membuat kelas Python kustom untuk model Anda. Ini memberikan kontrol penuh atas arsitektur model dan alur data.

4. Membuat Pipeline Data dengan tf.data
Bab ini berfokus pada cara efisien memuat dan memproses data untuk pelatihan. tf.data adalah API yang sangat direkomendasikan karena memungkinkan Anda membuat pipeline data yang dapat dioptimalkan.
Dataset: Sebuah objek tf.data.Dataset mewakili urutan elemen. API ini memungkinkan Anda untuk:
Memuat data dari berbagai sumber (file, memori).
Mentransformasi data (Seperti menormalisasi gambar, memproses teks).
Menggabungkan dan mengacak data untuk pelatihan.
ImageDataGenerator: Alternatif dari Keras yang mempermudah pemuatan gambar dari direktori dan melakukan augmentasi data dasar secara on-the-fly.

5. Arsitektur Jaringan Saraf
Bagian ini memperkenalkan beberapa arsitektur dasar yang paling penting.
Jaringan Terhubung Sepenuhnya (FCN): Juga dikenal sebagai feed-forward neural networks. Setiap neuron di satu lapisan terhubung ke setiap neuron di lapisan berikutnya. FCNs digunakan untuk tugas-tugas dasar seperti klasifikasi biner dan regresi.
Jaringan Saraf Konvolusional (CNN): Dirancang khusus untuk memproses data gambar. Mereka menggunakan lapisan konvolusi untuk mengekstrak fitur spasial dari gambar dan lapisan pooling untuk mereduksi dimensi.
Jaringan Saraf Berulang (RNN): Digunakan untuk data sekuensial atau deret waktu, di mana output saat ini juga bergantung pada input sebelumnya. RNNs memiliki "memori" internal yang memungkinkannya memproses urutan seperti teks atau data time-series.

Transformer: Model revolusioner yang pada awalnya dirancang untuk tugas NLP. Berbeda dari RNN, Transformer tidak mengandalkan pemrosesan berurutan. Sebaliknya, mereka menggunakan mekanisme self-attention untuk mempertimbangkan semua kata dalam sebuah kalimat secara bersamaan, memungkinkan mereka menangkap dependensi jarak jauh dengan lebih efisien.
