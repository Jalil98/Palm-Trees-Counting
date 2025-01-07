# Palm-Trees-Counting
Dengan memanfaatkan teknik computer vision, program secara otomatis mengidentifikasi dan menghitung jumlah pohon kelapa sawit. Gambar keluaran ini diharapkan dapat memudahkan pengelola perkebunan untuk memantau dan mengelola data inventaris pohon secara efisien.
------------------
**Notes**
1. python==3.9
2. Run with colab/jupyter notebook
3. windows
4. !pip install roboflow
5. !pip install ultralytics
6. !pip install opencv-python
------------------

**AI CYCLE PROJECT**

**1. Data Aquisisi**

Data yang digunakan adalah kumpulan gambar pohon kelapa sawit (*palm trees*) yang diperoleh dari Kaggle, terdiri dari 72 gambar. kemudian saya melabeli secara manual menggunakan RoboFlow, dengan anotasi kelas *palm-trees* pada setiap *bounding box*. Dataset kemudian dibagi menjadi tiga bagian: 70% untuk data pelatihan (*training*), 20% untuk validasi (*validation*), dan 10% untuk pengujian (*testing*). silahkan klik [dataset](https://app.roboflow.com/palm-trees-counting/palm-trees-counting/1/export) untuk mendownload dataset.

**2. Data Explorasi**

Pada proses eksplorasi data, saya melakukan *preprocessing* dengan mengubah ukuran gambar menjadi 480x480 piksel.

**3. Modelling**

Algoritma yang saya pake dalam membuat model ini adalah algoritma Yotov8 karena algoritma ini sangat cocok digunakan untuk mendeteksi objek secara real-time. model dilatih dengan epoch=100, imgsz=640 menghasilkan results precission=60%, Recall=53%, mAP=56%


**4. Evaluation**

Seperti pada penjelasan tahap modeling diatas, Model kemudian dilakukan evaluasi dengan teknik precission&Recall untuk membantu memahami keseimbangan deteksi antara benar dan salah. Selain itu, teknik evaluasi yang kami gunakan adalah mAP(mean Average Precission) guna untuk standarisasi dalam deteksi objek. persentase dari masing-masing metode evaluasi dijelaskan di tahap modeling. berikut hasil visualisasi dari masing-masing metode:

![P_curve](https://github.com/user-attachments/assets/b591a8e3-f104-481a-b09d-cc6991512acd)

![R_curve](https://github.com/user-attachments/assets/bbabf5f4-a9b9-4a22-88f0-a3c136e9fa1a)

![results](https://github.com/user-attachments/assets/0fcaab4e-3c18-44e1-819c-24e2e37e1f62)

**KESIMPULAN**
Model palm-trees counting yang saya buat perlu diperbaiki agar mendapatkan hasil mAP yang besar. kita bisa menambahkan dataset dan memperbaiki pada hapan labeling.
sementara itu, dari hasil uji coba dengan dataset gambar sebanyak 72 gambar bisa mendapatkan hasil yang cukup baik. Berikut hasil uji coba testing model dengan menggunakan salah satu sampel gambar. klik [gambar](https://storage.googleapis.com/648010c1-f244-4641-98f2-73ff6c1b4e99/ai_assignment_20241202_count.jpeg) berikut untuk uji coba. dan kami mendapatkan hasil deteksi yang cukup bagus meskipun kami perlu memperbaiki modelnya. hasil gambar testing seperti yang terlihat pada gambar dibawah ini:

 **output_non_angka**
 
 ![output_non_angka](https://github.com/user-attachments/assets/1fd18e98-ad26-49b1-95e8-9ceabd2ab27b)

 -----------------------------------------------------------------------------------------------------
 **Output_count**
 
![output_count](https://github.com/user-attachments/assets/fd4e7e64-6f50-4568-a9dc-cb47ee473e4b)
