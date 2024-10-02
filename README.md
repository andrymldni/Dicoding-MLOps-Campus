## Submission 2: Optimalisasi Seleksi Penerimaan Mahasiswa

Nama: Andry Syva Maldini<br>
Username dicoding: andrymldni

<p align="center">
  <img src="https://github.com/user-attachments/assets/aba7492f-11cf-46db-be13-a0cc27f182fb" alt="dataset-cover" width="600" height="350">
</p>

|                         | Deskripsi                                                                                                                                  |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| Dataset                 | [Campus Placement Prediction: Binary Classification](https://www.kaggle.com/datasets/meruvulikith/campus-selection-classification-dataset) |
| Masalah                 | Seleksi penerimaan universitas telah menjadi kegiatan penting bagi calon mahasiswa dengan latar belakang dan kemampuan yang beragam. Dengan banyaknya pelamar yang mendaftar, universitas sering kewalahan dalam memilih kandidat terbaik. Beberapa metode seleksi umum yang digunakan meliputi penulisan esai dan wawancara. Selain itu, riwayat pendidikan dan pengalaman kerja kandidat juga ditinjau, meskipun sering kali serupa satu sama lain. |
| Solusi machine learning | Penyaringan esai dan wawancara dapat dilakukan langsung oleh para profesional untuk mendapatkan hasil yang lebih baik, namun penyaringan nilai dan persyaratan administratif lainnya memiliki potensi kesalahan karena banyaknya informasi yang diterima sekaligus. Karena informasi ini sudah diterima sebelumnya, penerapan machine learning dapat membantu memberikan umpan balik awal pada hasil penyaringan kandidat untuk mempercepat proses seleksi. |
| Metode pengolahan       |   Dalam dataset tersebut, terdapat fitur-fitur seperti riwayat pendidikan, pengalaman kerja, dan status penerimaan (data asli juga mencakup nomor kandidat yang dihapus karena tidak digunakan). Status penerimaan ditetapkan sebagai variabel target (variabel target awalnya bersifat kategorikal, namun diubah menjadi numerik sebelum digunakan). Nilai variabel numerik diubah dengan penskalaan data (rentang 0-1) agar lebih konsisten. Kemudian, variabel kategorikal dikonversi menjadi angka menggunakan one-hot encoding agar dapat digunakan dalam pelatihan. Variabel target diubah menjadi bilangan bulat. Variabel yang dikonversi akan diberi nama baru dengan tambahan "_xf". Setelah proses transformasi, data dibagi menjadi data latih dan data uji dengan rasio 80:20. |
| Arsitektur model        | Arsitektur model dimulai dengan lapisan concatenate untuk menggabungkan fitur-fitur yang telah ditransformasikan, diikuti oleh lapisan Dense dengan 8 neuron dan aktivasi relu. Setelah itu, terdapat lapisan klasifikasi dengan Dense yang menggunakan aktivasi sigmoid, karena outputnya bersifat biner (0 atau 1). Dalam proses pelatihan, digunakan optimizer Adam dengan learning rate 0.001, loss binary crossentropy, dan metrik binary accuracy. Tipe biner dipilih karena kasus ini berfokus pada klasifikasi biner (2 kelas). |
| Metrik evaluasi         | Metrik evaluasi yang digunakan dalam kasus ini adalah Binary Accuracy dan Loss. |
| Performa model          | Model memiliki akurasi pelatihan 90.03% dan akurasi validasi 84.42%, menunjukkan performa yang baik namun ada indikasi overfitting karena perbedaan loss antara pelatihan (0.1766) dan validasi (0.3634). |
| Web app                 | [Campus Prediction](https://campus-prediction-production.up.railway.app/v1/models/campus-selection-model/metadata) (active) |
| Monitoring              | Pemantauan model dilakukan menggunakan platform Prometheus melalui Docker. Salah satu contoh pemantauan yang diterapkan pada model adalah menampilkan permintaan yang masuk. |
