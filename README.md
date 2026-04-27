# 🖼️ Image Classification (Deep Learning Project)

<p align="center">
  <a href="https://github.com/xebec51">
    <img src="https://img.shields.io/badge/GitHub-xebec51-blue?logo=github" />
  </a>
  <a href="https://www.linkedin.com/in/rinaldiruslan">
    <img src="https://img.shields.io/badge/LinkedIn-rinaldiruslan-0A66C2?logo=linkedin&logoColor=white" />
  </a>
  <a href="https://www.instagram.com/rinaldiruslan/">
    <img src="https://img.shields.io/badge/Instagram-rinaldiruslan-E4405F?logo=instagram" />
  </a>
  <a href="https://www.tiktok.com/@rinaldiruslan">
    <img src="https://img.shields.io/badge/TikTok-rinaldiruslan-000000?logo=tiktok&logoColor=white" />
  </a>
  <br/>
  <a href="https://opensource.org/licenses/MIT">
    <img src="https://img.shields.io/badge/License-MIT-blue.svg" />
  </a>
  <img src="https://img.shields.io/badge/Deep%20Learning-Computer%20Vision-orange" />
</p>

---

🌐 **Submission dari Kelas**:  
[Belajar Fundamental Deep Learning - Dicoding](https://www.dicoding.com/academies/185/)

📌 **Submission ke-2 (Final Project) dari kelas ini**

---

## 📌 Deskripsi Proyek

Proyek ini merupakan implementasi **klasifikasi gambar berbasis Deep Learning (Computer Vision)** untuk mengidentifikasi berbagai jenis hewan.

Model dikembangkan menggunakan pendekatan **Convolutional Neural Network (CNN)** dengan teknik **transfer learning**, sehingga mampu mencapai performa tinggi pada dataset dengan kompleksitas visual yang beragam.

---

## 🚀 Key Highlights

* ✅ Dataset besar (>26.000 gambar)
* ✅ 10 kelas objek (multi-class classification)
* ✅ Variasi resolusi gambar (real-world scenario)
* ✅ Data augmentation (rotation, zoom, flip)
* ✅ Transfer learning (MobileNetV2)
* ✅ Fine-tuning model
* ✅ Callback optimization (EarlyStopping, ReduceLROnPlateau)
* ✅ Evaluasi lengkap:
  * Accuracy
  * Classification Report
  * Confusion Matrix
* ✅ Model conversion:
  * SavedModel
  * TensorFlow Lite (TFLite)
  * TensorFlow.js (TFJS)
* ✅ Inference pada data baru

---

## 📊 Dataset Overview

Dataset yang digunakan adalah **Animals-10 Dataset** dari Kaggle:

🔗 https://www.kaggle.com/datasets/antobenedetti/animals

### 📌 Informasi Dataset:

* Total gambar: **26.179**
* Jumlah kelas: **10**
  * cane (anjing)
  * cavallo (kuda)
  * elefante (gajah)
  * farfalla (kupu-kupu)
  * gallina (ayam)
  * gatto (kucing)
  * mucca (sapi)
  * pecora (domba)
  * ragno (laba-laba)
  * scoiattolo (tupai)

Dataset memiliki **variasi resolusi tinggi**, sehingga dilakukan preprocessing untuk menyeragamkan ukuran gambar.

---

## ⚙️ Metodologi

### 1. Data Preparation
* Data extraction & exploration
* Train/Validation/Test split (70/15/15)

---

### 2. Data Preprocessing
* Rescaling (normalisasi pixel)
* Data augmentation pada data latih

---

### 3. Modeling

Proyek ini menggunakan dua pendekatan model:

#### 1) CNN (Sequential Model)
Model CNN baseline dibangun menggunakan:
* Conv2D
* MaxPooling2D
* Dense Layer

Alasan pemilihan model ini:
* Menjadi baseline arsitektur **Sequential** untuk evaluasi komparatif antar pendekatan model.
* Layer **Conv2D + MaxPooling2D** digunakan untuk mengekstraksi fitur lokal (tekstur, tepi, pola bentuk) secara hierarkis.
* Menjadi baseline yang representatif untuk mengukur peningkatan performa saat beralih ke transfer learning.

Model ini digunakan sebagai baseline arsitektur vision yang terukur, dengan komponen inti **Sequential**, **Conv2D**, dan **Pooling layer**, serta capaian akurasi di atas batas minimum yang ditetapkan.

#### 2) Transfer Learning (MobileNetV2)
Model utama menggunakan **MobileNetV2** sebagai base model dengan tambahan fully connected layer.

Alasan pemilihan MobileNetV2:
* Arsitektur ringan dan efisien komputasi, cocok untuk dataset menengah-besar serta proses fine-tuning.
* Bobot pra-latih dari ImageNet memberi representasi fitur visual yang kuat, sehingga konvergensi lebih stabil.
* Secara praktis unggul untuk deployment lintas platform (SavedModel, TFLite, TFJS) dengan trade-off akurasi-kompleksitas yang baik.

Arsitektur model utama:
* Base Model (MobileNetV2)
* Global Average Pooling
* Dense Layer + Dropout
* Output Layer (Softmax - 10 kelas)

---

### 4. Training Strategy
* Initial training (freeze base model)
* Fine-tuning (unfreeze sebagian layer)
* Callback:
  * EarlyStopping
  * ReduceLROnPlateau
  * ModelCheckpoint

---

## 📊 Model Performance

* CNN (Baseline):
  * Training Accuracy: ~86-87%
  * Validation Accuracy: ~86-87%
  * Test Accuracy: **86.08%**
* MobileNetV2 (Best Model):
  * Training Accuracy: ~97%
  * Validation Accuracy: ~96-97%
  * Test Accuracy: **96.46%**

📌 MobileNetV2 memberikan performa terbaik dengan generalisasi yang baik pada data validasi dan data uji.

### ✅ Kesesuaian Kriteria Teknis

Seluruh poin teknis inti pada submission telah dipenuhi secara eksplisit:
* Menggunakan arsitektur **Sequential** pada model CNN baseline.
* Mengimplementasikan layer **Conv2D** dan **Pooling** (MaxPooling2D).
* Melakukan evaluasi pada data uji terpisah (test set).
* Mencapai akurasi >85% pada model utama, bahkan baseline CNN juga melewati ambang minimum.

Ringkasan hasil terhadap ambang akurasi:
* CNN Baseline: **86.08%** (melewati ambang >85%).
* MobileNetV2: **96.46%** (model terbaik).

### 🏁 Model Selection (Pemilihan Model Terbaik)

Pemilihan model akhir didasarkan pada evaluasi kuantitatif dan pertimbangan generalisasi:
* Selisih akurasi uji antara MobileNetV2 dan CNN baseline adalah **+10.38 poin persentase** (96.46% vs 86.08%).
* Kinerja validasi MobileNetV2 konsisten pada rentang tinggi (96-97%), mengindikasikan gap generalisasi yang rendah.
* Dengan konfigurasi fine-tuning terkontrol, MobileNetV2 memberikan kompromi terbaik antara akurasi, stabilitas training, dan kesiapan deployment.

Berdasarkan temuan tersebut, **MobileNetV2 ditetapkan sebagai final model** untuk proses evaluasi lanjutan, inferensi, dan konversi format model.

---

## 📦 Model Export

Model disimpan dalam beberapa format:
* SavedModel
* TensorFlow Lite (.tflite)
* TensorFlow.js (TFJS)

---

## 🔍 Insight Utama

* Peningkatan kinerja yang signifikan pada MobileNetV2 menunjukkan bahwa representasi fitur pra-latih lebih efektif dibanding pembelajaran dari nol pada domain visual yang beragam.
* Data augmentation berperan sebagai regularisasi implisit, menurunkan sensitivitas model terhadap variasi orientasi dan skala objek.
* Konsistensi metrik validasi dan uji mengindikasikan kemampuan generalisasi yang baik, bukan sekadar overfitting pada data latih.
* Error residual cenderung muncul pada pasangan kelas dengan kemiripan morfologi/tekstur, yang secara empiris umum pada skenario multi-class fine-grained classification.
* Secara metodologis, penggunaan baseline CNN tetap penting karena memberikan pembanding yang objektif untuk mengukur nilai tambah transfer learning.

---

## 📂 Struktur Proyek

```bash
.
├── notebook.ipynb
├── notebook.pdf
├── requirements.txt
│
├── saved_model/
├── tfjs_model/
├── tflite/
│   ├── model.tflite
│   └── label.txt
│
├── best_model.keras
└── README.md
```

---

## ▶️ Cara Menjalankan

### 1. Clone repository

```bash
git clone https://github.com/xebec51/image-classification-animals.git
```

### 2. Masuk ke folder

```bash
cd image-classification-animals
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Jalankan notebook

```bash
notebook.ipynb
```

---

## 🛠️ Teknologi yang Digunakan

* Python
* TensorFlow / Keras
* NumPy
* Matplotlib
* Scikit-learn
* Pillow

---

## 👤 Author

**Muh. Rinaldi Ruslan**

* 💻 GitHub: [https://github.com/xebec51](https://github.com/xebec51)
* 💼 LinkedIn: [https://www.linkedin.com/in/rinaldiruslan](https://www.linkedin.com/in/rinaldiruslan)
* 📸 Instagram: [https://www.instagram.com/rinaldiruslan/](https://www.instagram.com/rinaldiruslan/)
* 🎵 TikTok: [https://www.tiktok.com/@rinaldiruslan](https://www.tiktok.com/@rinaldiruslan)

---

## 📄 Lisensi

Proyek ini dilisensikan di bawah **MIT License**.