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

Model ini digunakan sebagai baseline dan untuk memenuhi kriteria penggunaan arsitektur CNN.

#### 2) Transfer Learning (MobileNetV2)
Model utama menggunakan **MobileNetV2** sebagai base model dengan tambahan fully connected layer.

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
  * Accuracy: ~59%
* MobileNetV2 (Best Model):
  * Training Accuracy: ~97%
  * Validation Accuracy: ~96-97%
  * Test Accuracy: ~96%

📌 MobileNetV2 memberikan performa terbaik dengan generalisasi yang baik pada data validasi dan data uji.

---

## 📦 Model Export

Model disimpan dalam beberapa format:
* SavedModel
* TensorFlow Lite (.tflite)
* TensorFlow.js (TFJS)

---

## 🔍 Insight Utama

* Transfer learning sangat efektif untuk dataset gambar kompleks
* Data augmentation membantu meningkatkan generalisasi
* Model mampu membedakan sebagian besar kelas dengan akurasi tinggi
* Kesalahan kecil terjadi pada kelas dengan kemiripan visual

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
````

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