# Final Project Oprec PENSHIP - Khamdi Alfin Mualif (4126600097)

## Identitas
- **Nama:** Khamdi Alfin Mualif
- **NRP:** 4126600097
- **Program studi:** D4 Mekatronika, Politeknik Elektronika Negeri Surabaya (PENS)

## Project Roboflow
- **Project ID Roboflow:** TODO — isi dengan `workspace/project`
- **Dataset version:** TODO — isi nomor versi dataset yang digunakan untuk Model 1
- **Link Roboflow Universe:** TODO — isi tautan publik proyek Roboflow

## Dataset
- **Kelas objek:** `bottle`, `laptop`, dan `pencil`.
- **Jumlah foto asli:** TODO — isi jumlah foto yang diambil sendiri.
- **Metode pengambilan foto:** TODO — jelaskan variasi jarak, sudut pengambilan, pencahayaan, dan latar belakang yang benar-benar digunakan.
- **AI labeling Roboflow:** TODO — jelaskan apakah menggunakan fitur AI labeling dan bagaimana label diperiksa atau diperbaiki.
- **Pembagian dataset:** TODO — isi jumlah gambar train, validation, dan test berdasarkan versi dataset Model 1.

Dataset digunakan untuk melatih model deteksi objek yang dapat mengenali botol plastik, laptop, dan pensil kayu. Pelabelan mengikuti definisi kelas yang ditetapkan dalam panduan final project PENSHIP.

## Training
- **Lingkungan training:** Google Colab dengan GPU T4.
- **Framework:** Ultralytics YOLOv8.
- **Model:** YOLOv8n.
- **Epochs:** 50.
- **Image size:** 640 × 640 piksel.
- **Batch size:** 16.
- **Optimizer:** Auto.
- **Bobot model yang digunakan:** `best.pt` dari Model 1, sebelum penambahan dataset pensil.
- **Grafik dan hasil training:** tersedia di folder `grafik/`.

Model 1 dipilih sebagai model final karena hasil evaluasi awalnya menunjukkan nilai mAP@50 dan mAP@50–95 lebih tinggi daripada Model 2 yang dilatih setelah dataset diperbarui.

### Metrik Model 1

| Metrik | Hasil |
|---|---:|
| Precision | 0.604 |
| Recall | 0.730 |
| mAP@50 | 0.760 |
| mAP@50–95 | 0.542 |

Nilai tersebut merupakan hasil evaluasi Model 1 yang dicatat selama eksperimen awal.

## Pengembangan Kode

Pengembangan dilakukan untuk melengkapi kode dasar training YOLOv8 dengan evaluasi dan pengujian model. Isi bagian ini harus disesuaikan dengan fitur yang benar-benar sudah ditambahkan dan diuji pada notebook final.

1. **Evaluasi model:** menampilkan metrik Precision, Recall, mAP@50, dan mAP@50–95 agar performa model dapat dinilai secara terukur.
2. **Pengujian inferensi:** menguji model pada gambar baru dan menampilkan bounding box, nama kelas, serta confidence hasil deteksi.
3. **Pencatatan hasil prediksi:** menyimpan hasil deteksi ke CSV agar prediksi per gambar dapat diperiksa lebih lanjut.
4. **Analisis kesalahan:** memeriksa hasil deteksi untuk menemukan objek yang tidak terdeteksi atau prediksi yang perlu dievaluasi kembali.

Pengembangan tersebut ditujukan untuk mempermudah evaluasi dan analisis performa model. Pengujian tambahan tidak dianggap sebagai hasil eksperimen sampai benar-benar dijalankan dan dicatat.

## Hasil Eksperimen

| No | Skenario | Epochs | Batch | Optimizer | mAP50 | mAP50-95 | Keterangan |
|:--:|:---|:---:|:---:|:---:|:---:|:---:|:---|
| 0 | Model 1 — dataset sebelum penambahan foto pensil | 50 | 16 | Auto | 0.760 | 0.542 | Dipilih sebagai model final |
| 1 | Model 2 — dataset setelah penambahan foto pensil | 50 | 16 | Auto | 0.717 | 0.433 | Tidak dipilih |

Eksperimen menunjukkan bahwa penambahan foto pensil pada dataset versi kedua tidak meningkatkan metrik keseluruhan model. Oleh karena itu, Model 1 dipertahankan sebagai model final untuk proyek ini.

## Struktur Repository

```text
FP_Khamdi-Alfin-Mualif_4126600097/
├── train_colab.ipynb
├── best.pt
├── README.md
└── grafik/
    ├── results.png
    ├── results.csv
    ├── confusion_matrix.png
    └── BoxPR_curve.png
```

Jika grafik precision–recall menggunakan nama `PR_curve.png`, gunakan nama file yang benar-benar tersedia. Notebook yang dikumpulkan harus berisi kode dasar yang telah dikembangkan.

## Kesimpulan

Proyek ini menerapkan YOLOv8 untuk mendeteksi tiga kelas objek sehari-hari, yaitu botol plastik, laptop, dan pensil kayu. Berdasarkan eksperimen yang dilakukan, Model 1 menghasilkan mAP@50 sebesar 0.760 dan mAP@50–95 sebesar 0.542 sehingga dipilih sebagai model final.

Pengembangan evaluasi, inferensi, dan pencatatan hasil prediksi ditujukan untuk membantu memahami performa model serta menjadi dasar perbaikan selanjutnya.

## Referensi
- Ultralytics YOLOv8: https://docs.ultralytics.com/
- Roboflow: https://roboflow.com/
- Project Roboflow: TODO — masukkan tautan publik proyek yang digunakan.
