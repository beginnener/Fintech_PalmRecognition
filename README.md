# Palmprint Recognition dengan SimpleCNN dan MobileNet

**Disusun oleh: Kelompok 99**
* **Natasha Adinda Cantika** (2312120)
* **Futih Millati Addinillah** (2309445)

---

## 📝 Deskripsi Proyek

Proyek ini adalah sistem identifikasi biometrik yang memanfaatkan karakteristik unik pada telapak tangan (*palmprint*), seperti garis utama (*principal lines*), kerutan (*wrinkles*), dan tekstur kulit. Sistem ini bertujuan untuk membangun model yang *robust* (tangguh) dalam mengenali identitas subjek meskipun terdapat *noise*, variasi pencahayaan, atau perbedaan kualitas kamera.

Dalam eksperimen ini, kami membandingkan pendekatan arsitektur *Deep Learning* untuk mengenali pola identitas subjek dari citra telapak tangan.

## 🧠 Metodologi

Sistem bekerja dengan mengekstraksi fitur morfologi dari citra telapak tangan yang kemudian dipelajari oleh model. Kami bereksperimen dengan desain berikut:

1.  **SimpleCNN (Baseline):** Arsitektur *Convolutional Neural Network* (CNN) sederhana yang digunakan sebagai titik acuan untuk menguji kemampuan algoritma konvensional.
2.  **MobileNetV2:** Model yang dipilih karena efisiensinya menggunakan *depthwise separable convolutions*, menjadikannya ringan dan cepat, ideal untuk perangkat *mobile*.

## 📂 Dataset

Dataset yang digunakan adalah **Birjand University Mobile Palmprint Database (BUMP)** yang bersumber dari Kaggle.

* **Klasifikasi:** Terdiri dari berbagai kelas (individu).
* **Variasi Sesi:** Mencakup foto dari Sesi 1 (kode `f`/first) dan Sesi 2 (kode `s`/second).
* **Lateralitas:** Mencakup citra tangan kanan dan tangan kiri untuk setiap subjek.
* **Preprocessing:** Citra diubah ukurannya (*resize*) menjadi **225x225** dengan metode *padding* untuk menjaga rasio aspek gambar.

## 🛠️ Persyaratan Sistem (Requirements)

Proyek ini dibuat menggunakan Python di lingkungan Google Colab. Berikut adalah *library* utama yang digunakan:

* `tensorflow`
* `opencv-python` (cv2)
* `numpy`
* `matplotlib` & `seaborn`
* `scikit-learn`
* `gdown` (untuk mengunduh dataset)

## 🚀 Cara Menjalankan

1.  **Persiapan Lingkungan:**
    Disarankan menjalankan *notebook* ini di Google Colab dengan *Runtime* GPU.

2.  **Download Dataset:**
    Notebook ini dilengkapi skrip otomatis untuk mengunduh dataset dari Google Drive (ID: `1XgPtdtaCAsJ78uszoFHb4hhcEt8Jqe0k`) dan mengekstraknya ke folder `/content/dataset_raw`.

3.  **Preprocessing & Loading:**
    Jalankan sel kode untuk memuat gambar, melakukan *resize with padding*, dan membagi dataset menjadi data latih (*train*) dan uji (*test*).

4.  **Training Model:**
    Jalankan sel pelatihan untuk melatih model SimpleCNN.
    > **Catatan:** Untuk eksperimen ini, *Random Seed* dikunci pada angka **42** agar hasil konsisten.

## 📊 Hasil dan Kendala

* **SimpleCNN:** Berhasil diimplementasikan sebagai *baseline*.
* **MobileNet:** Implementasi *fine-tuning* pada MobileNet mengalami kendala keterbatasan **RAM** pada lingkungan Google Colab versi gratis, sehingga fokus utama dialihkan pada optimalisasi SimpleCNN.

## 🔗 Referensi

* **Dataset:** Birjand University Mobile Palmprint Database (BUMP)
* **Algoritma ROI:** [CyberNord/ROI-Extraction-for-Palmprint-Recognition](https://github.com/CyberNord/ROI-Extraction-for-Palmprint-Recognition/)