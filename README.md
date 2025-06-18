# Perbandingan Analisis MANOVA dan MANCOVA: Pengaruh Faktor Sosial dan Akademik terhadap Performa Siswa Sekolah Menengah

## Deskripsi Proyek

Proyek ini bertujuan untuk menganalisis pengaruh berbagai faktor sosial dan akademik terhadap performa akademik siswa sekolah menengah menggunakan data dari mata pelajaran Matematika. Analisis utama membandingkan hasil dari Multivariate Analysis of Variance (MANOVA) dan Multivariate Analysis of Covariance (MANCOVA) untuk memahami bagaimana faktor-faktor seperti waktu belajar, kesehatan, dukungan keluarga, dan lainnya memengaruhi nilai siswa (G1, G2, G3), serta bagaimana pengaruh kovariat seperti usia dan jumlah absensi mengubah kesimpulan.

## Dataset

Analisis ini menggunakan dataset student-mat.csv yang berisi data demografi siswa, atribut sosial, dan performa akademik dari sebuah sekolah di Portugal. Variabel yang digunakan meliputi:

**Variabel Independen (Faktor)**:

- sex: Jenis kelamin siswa

- studytime: Waktu belajar mingguan

- goout: Frekuensi keluar rumah dengan teman

- famsup: Dukungan pendidikan dari keluarga

- health: Status kesehatan saat ini

- romantic: Status hubungan romantis

- (failures: Jumlah kegagalan kelas sebelumnya - dihapus saat analisis karena melanggar asumsi homogenitas)

**Variabel Dependen (Ukuran Performa)**:

- G1: Nilai periode pertama

- G2: Nilai periode kedua

- G3: Nilai akhir

**Kovariat (untuk MANCOVA)**:

- age: Usia siswa

- absences: Jumlah absensi sekolah

Sumber Dataset: https://archive.ics.uci.edu/dataset/320/student+performance

## Proses Analisis

Analisis dalam file R Markdown (hasilproject_RMarkdown.Rmd) mencakup langkah-langkah berikut:

1.Pemuatan dan Pemeriksaan Data: Membaca dataset, memilih variabel relevan, mengubah tipe data variabel independen menjadi faktor, dan memeriksa missing values.

2.Uji Asumsi Awal: Melakukan uji normalitas univariat (Shapiro-Wilk) dan multivariat (Henze-Zirkler), uji homogenitas matriks kovarians (Box's M), uji linearitas antara variabel dependen dan kovariat, serta pemeriksaan multikolinearitas antar kovariat.

3.Perbaikan Asumsi: Menangani outlier menggunakan metode IQR dan melakukan transformasi Box-Cox pada variabel dependen (G1, G2, G3) untuk mendekati normalitas.

4.Uji Asumsi Kembali: Mengulangi uji asumsi setelah penanganan outlier dan transformasi. Berdasarkan hasil uji homogenitas Box's M, variabel failures dihapus dari analisis.

5.Analisis MANOVA: Menjalankan model MANOVA untuk menguji pengaruh variabel independen (faktor) terhadap kombinasi variabel dependen (G1, G2, G3) tanpa mempertimbangkan kovariat.

6.Analisis MANCOVA: Menjalankan model MANCOVA untuk menguji pengaruh variabel independen terhadap variabel dependen, dengan mengontrol pengaruh kovariat (age dan absences).

## Hasil Utama

**MANOVA**: Menunjukkan bahwa studytime (waktu belajar) dan health (kesehatan) memiliki pengaruh signifikan secara statistik terhadap kombinasi nilai G1, G2, dan G3. Faktor lain seperti sex, goout, famsup, dan romantic tidak menunjukkan pengaruh signifikan.

**MANCOVA**: Setelah mengontrol variabel age (usia) dan absences (jumlah absensi), analisis menunjukkan bahwa studytime, health, age, dan absences memiliki pengaruh signifikan terhadap performa akademik siswa. Siswa dengan waktu belajar lebih lama, kesehatan lebih baik, usia tertentu (kemungkinan terkait kematangan), dan jumlah absensi lebih sedikit cenderung memiliki nilai lebih baik. Faktor sex, goout, famsup, dan romantic tetap tidak signifikan.

Perbandingan antara MANOVA dan MANCOVA menyoroti pentingnya mempertimbangkan kovariat. Usia dan absensi terbukti menjadi faktor penting yang memengaruhi performa akademik, dan mengontrolnya memberikan pemahaman yang lebih akurat tentang pengaruh faktor lainnya.

## Cara Menjalankan

Untuk mereplikasi analisis ini:

1.Pastikan Anda memiliki R dan RStudio (atau environment R lainnya) terinstal.

2.Instal paket R yang diperlukan

3.Unduh file hasilproject_RMarkdown.Rmd dan dataset student-mat.csv.

4.Letakkan kedua file dalam direktori kerja yang sama.

5.Buka file .Rmd di RStudio dan jalankan semua code chunk atau gunakan tombol "Knit" untuk menghasilkan dokumen output (misalnya, Word).

## Kontributor

Dimas Fatkhul Rahman (@dimasszeeh)

Fadhil Muhammad (@fadhilmu)

Putri Manika Rukmamaya (@putri-manika)
