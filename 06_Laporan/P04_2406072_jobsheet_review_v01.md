# LAPORAN PRAKTIKUM ANALISIS DAN DESAIN BERORIENTASI OBJEK
**Pertemuan 4: Use Case Diagram Lanjutan (Generalization dan Collaboration)**  
**Program Studi:** S1 Teknik Informatika – Institut Teknologi Garut  
**Kode Mata Kuliah:** IFRWP5149  

---

## 1. Tujuan Praktikum
Setelah melaksanakan praktikum pada Pertemuan 4, mahasiswa diharapkan mampu:
1. **Generalization Aktor:** Mengidentifikasi satu aktor umum dan minimal dua aktor khusus dari skenario, lalu menyusun hierarki pewarisan dengan arah panah yang tepat (segitiga kosong dari aktor khusus ke aktor umum) tanpa menggambar ulang asosiasi yang diwarisi.
2. **Generalization Use Case:** Menyusun hierarki *use case* yang memuat satu *use case* umum dan minimal dua *use case* khusus, serta mendefinisikan perilaku yang diwarisi dan perilaku pembedanya.
3. **Collaboration & Realization:** Menempatkan minimal dua *collaboration* (elips garis putus-putus) dengan nama yang identik dengan *use case* yang direalisasikan, dan menghubungkannya menggunakan relasi *realization* (garis putus-putus berujung segitiga kosong) dari *collaboration* menuju *use case*.
4. **Diagram Kumulatif:** Membangun *use case diagram* kumulatif Pertemuan 4 (mempertahankan elemen Pertemuan 3 secara utuh dan menambahkan elemen baru Pertemuan 4) dengan penempatan aktor di luar batas sistem serta *use case*/*collaboration* di dalam batas sistem.
5. **Use Case Description:** Menyusun deskripsi *use case* baru secara lengkap (*pemicu, prasyarat, alur utama, alur alternatif, pascakondisi berhasil/gagal*, serta baris tambahan *Generalization* dan *Collaboration*) yang konsisten dengan diagram.
6. **Keterlacakan & Revisi:** Menunjukkan keterlacakan (*traceability*) setiap elemen baru ke daftar kebutuhan, melakukan uji konsistensi/review, dan mendokumentasikan revisi ke versi berikutnya (`v02`).

---

## 2. Dasar Teori
1. **Pengembangan Model Kumulatif (OMG UML 2.5.1):**  
   *Use case diagram* menyajikan interaksi antara aktor dan sistem tanpa merinci urutan langkah teknis atau rancangan antarmuka. Pada rangkaian praktikum ini, pemodelan dilakukan secara **kumulatif**—artinya model dari pertemuan sebelumnya tidak dihapus atau ditimpa, melainkan dipertahankan dan diperluas dengan elemen baru agar riwayat perubahan dapat dilacak dengan jelas.
2. **Generalization Aktor:**  
   Menyatakan hubungan umum-khusus antarperan. Aktor khusus mewarisi seluruh asosiasi yang dimiliki aktor umum, namun tetap dapat memiliki asosiasi tambahan yang eksklusif bagi dirinya sendiri. Panah segitiga kosong selalu mengarah dari aktor khusus ke aktor umum, dan asosiasi warisan cukup digambar satu kali dari aktor umum.
3. **Generalization Use Case:**  
   Menyatakan bahwa satu *use case* khusus merupakan bentuk spesifik dari *use case* umum. *Use case* khusus mewarisi tujuan dan perilaku dasar dari *use case* umum, lalu menyesuaikan atau menambahkan hasil akhir yang lebih spesifik. Berbeda dengan `«include»` dan `«extend»` yang menyatakan hubungan pelaksanaan perilaku, *generalization* menyatakan hubungan jenis (*is-a-kind-of*).
4. **Collaboration dan Realization:**  
   *Collaboration* merepresentasikan sekumpulan elemen di dalam sistem yang bekerja sama untuk mewujudkan perilaku suatu *use case* (menjawab *bagaimana* perilaku diwujudkan secara abstrak pada tahap analisis). Digambarkan sebagai elips bergaris putus-putus dengan nama yang sama persis dengan *use case* targetnya, tidak terhubung langsung dengan aktor, dan dihubungkan ke *use case* menggunakan panah *realization* (garis putus-putus berujung segitiga kosong).

---

## 3. Hasil Praktikum
Praktikum dilaksanakan pada dua domain kasus dengan struktur direktori standar `IFRWP5149_<NIM>_LabAlat/` dan penamaan berkas `P04_<NIM>_<KASUS>_usecase_v01.drawio` (beserta ekspor `.png`).

### A. Studi Kasus Terbimbing: Sistem Informasi Peminjaman & Pengembalian Peralatan Laboratorium (LAB)
Model ini merupakan kelanjutan kumulatif dari Pertemuan 3 (`LAB-UC01` s.d. `LAB-UC07`) dengan penambahan kebutuhan `LAB-R07` s.d. `LAB-R11`:
* **Hierarki Aktor (*Generalization*):**
  * **Aktor Umum:** `Peminjam` (terhubung ke `LAB-UC01: Lihat Ketersediaan Peralatan` dan `LAB-UC03: Ajukan Peminjaman`).
  * **Aktor Khusus:** `Mahasiswa` (mewarisi asosiasi `Peminjam` + mempertahankan asosiasi khusus ke `LAB-UC05: Cetak Bukti Pengajuan`) dan `Dosen` (mewarisi asosiasi `Peminjam`).
* **Hierarki Use Case (*Generalization*):**
  * **Use Case Umum:** `LAB-UC02: Kelola Data Peralatan` (terhubung ke `Petugas Laboratorium`).
  * **Use Case Khusus:** `LAB-UC08: Tambah Data Peralatan` (menghasilkan data baru), `LAB-UC09: Ubah Data Peralatan` (memperbarui data), dan `LAB-UC10: Hapus Data Peralatan` (menghapus data yang tidak sedang dipinjam/diajukan).
* **Use Case Baru & Relasi:**
  * `LAB-UC11: Catat Pengembalian Peralatan` (terhubung ke `Petugas Laboratorium`) memiliki relasi `«include»` menuju `LAB-UC12: Periksa Kondisi Peralatan` (mencatat kondisi: *Baik*, *Rusak Ringan*, atau *Rusak Berat*).
* **Collaboration & Realization:**
  * `LAB-CO01: Ajukan Peminjaman` merealisasikan `LAB-UC03`.
  * `LAB-CO02: Catat Pengembalian Peralatan` merealisasikan `LAB-UC11`.
* **Dokumentasi Tambahan:** *Use case description* lengkap untuk `LAB-UC11` serta pencatatan aturan keterlambatan dan denda sebagai *pertanyaan terbuka* pada berkas kebutuhan.

### B. Tugas Praktik Mandiri: Sistem Informasi Akademik – Layanan Hasil Studi (SIA)
Model kumulatif yang menggabungkan fungsi Jadwal Kuliah (Pertemuan 2: `SIA-UC01`–`02`), Pengajuan KRS (Pertemuan 3: `SIA-UC03`–`06`), dan Layanan Hasil Studi (Pertemuan 4: `SIA-R07` s.d. `SIA-R12`):
* **Hierarki Aktor (*Generalization*):**
  * **Aktor Umum:** `Civitas Akademika` (berasosiasi dengan `SIA-UC07: Lihat Kalender Akademik`).
  * **Aktor Khusus:** `Mahasiswa` (mewarisi fungsi `Civitas Akademika`, memiliki fungsi KRS dari P03, serta terhubung ke `SIA-UC09: Lihat KHS`) dan `Dosen` (mewarisi fungsi `Civitas Akademika` serta terhubung ke `SIA-UC08: Input Nilai Mata Kuliah`).
  * Aktor lain yang tetap dipertahankan: `Admin Akademik` dan `Dosen Wali`.
* **Hierarki Use Case (*Generalization*):**
  * **Use Case Umum:** `SIA-UC10: Kelola Data Mahasiswa` (berasosiasi dengan `Admin Akademik`).
  * **Use Case Khusus:** `SIA-UC11: Tambah Data Mahasiswa`, `SIA-UC12: Ubah Data Mahasiswa`, dan `SIA-UC13: Hapus Data Mahasiswa` (dengan syarat tidak memiliki data akademik aktif).
* **Collaboration & Realization:**
  * `SIA-CO01: Input Nilai Mata Kuliah` merealisasikan `SIA-UC08`.
  * `SIA-CO02: Lihat KHS` merealisasikan `SIA-UC09`.

---

## 4. Analisis
1. **Efisiensi Model melalui Pewarisan (Generalization):**  
   Penerapan *generalization* pada aktor (`Peminjam` pada LAB dan `Civitas Akademika` pada SIA) berhasil mengurangi duplikasi garis asosiasi pada diagram. Meskipun garis asosiasi dari `Mahasiswa` ke `Lihat Ketersediaan` dan `Ajukan Peminjaman` dipindahkan ke `Peminjam`, secara semantik kemampuan `Mahasiswa` tidak hilang karena diwariskan secara otomatis. Sementara itu, fungsi unik seperti `Cetak Bukti Pengajuan` tetap dipertahankan sebagai asosiasi langsung pada aktor khusus `Mahasiswa`.
2. **Pemisahan Konteks Relasi (`Generalization` vs `«include»` / `«extend»`):**  
   Pada studi kasus LAB, terlihat jelas perbedaan semantik antar-relasi: `Tambah`, `Ubah`, dan `Hapus Data Peralatan` merupakan spesialisasi jenis dari `Kelola Data Peralatan` (*generalization*), sedangkan `Periksa Kondisi Peralatan` adalah langkah wajib yang selalu dieksekusi di dalam proses `Catat Pengembalian Peralatan` (`«include»`).
3. **Kejelasan Abstraksi Realisasi (*Collaboration*):**  
   Penambahan elemen *collaboration* (`LAB-CO01`, `LAB-CO02`, `SIA-CO01`, `SIA-CO02`) memberikan penanda visual bahwa *use case* utama tersebut memiliki mekanisme kerja sama objek internal yang akan dirinci lebih lanjut pada diagram interaksi (seperti *Sequence Diagram*) di pertemuan berikutnya, tanpa mengacaukan batas interaksi aktor di luar sistem.
4. **Validasi Batasan Sistem & Uji Konsistensi:**  
   Melalui pengujian skenario (seperti penolakan input nilai oleh dosen non-pengampu, penolakan hapus data mahasiswa yang masih aktif, serta pengecekan bahwa `Kepala Laboratorium` tetap hanya terhubung ke `LAB-UC07` tanpa relasi tambahan), terbukti bahwa diagram kumulatif dan *use case description* telah konsisten terhadap spesifikasi kebutuhan (`R01`–`R12`).

---

## 5. Kesimpulan
1. Penerapan **generalization aktor** dan **generalization use case** membuat *use case diagram* lebih ringkas, terstruktur, dan bebas dari redudansi asosiasi untuk peran maupun fungsi yang berbagi perilaku dasar yang sama.
2. Notasi **collaboration** dan relasi **realization** berfungsi menjembatani spesifikasi perilaku eksternal (*use case*) dengan rancangan interaksi internal sistem pada tahap analisis, dengan tetap menjaga aturan bahwa aktor tidak pernah berinteraksi langsung dengan *collaboration*.
3. Pendekatan pengembangan model secara **kumulatif** dan terdokumentasi (melalui katalog *use case*, *use case description* yang diperbarui, serta kontrol versi `v01` ke `v02`) menjamin keterlacakan (*traceability*) yang utuh antara kebutuhan fungsional lama dan baru tanpa merusak artefak pertemuan sebelumnya.