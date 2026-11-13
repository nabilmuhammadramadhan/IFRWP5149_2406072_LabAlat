# JOBSHEET REVIEW PRAKTIKUM PERTEMUAN 6
**Activity Diagram: Dari Skenario ke Alur Aktivitas**

## 1. Identitas & Metadata Praktikum
* **Nama Mahasiswa:** Nabil Muhammad Ramadhan
* **NIM:** 2406072
* **Mata Kuliah:** Praktikum Analisis dan Desain Berorientasi Objek (IFRWP5149)
* **Institusi:** Institut Teknologi Garut – S1 Teknik Informatika
* **Pertemuan:** 6 (Activity Diagram)
* **Repositori GitHub:** `IFRWP5149_2406072_LabAlat`
* **Lokasi Penyimpanan Berkas:** `06_Laporan/P06_2406072_jobsheet_review_v01.md`

---

## 2. Tujuan Pembelajaran
Setelah mengikuti praktikum pertemuan ke-6 ini, mahasiswa mampu:
1. Menyusun alur utama (*main flow*) sebuah *Activity Diagram* dari **Skenario Normal** pada tabel skenario Pertemuan 5 dengan tepat satu *initial node*, urutan *action* yang sesuai langkah skenario, dan minimal satu *activity final node* tanpa alur yang terputus (**Indikator 4.1**).
2. Mengubah **Skenario Alternative** menjadi cabang *decision* berlabel *guard* yang saling lepas dan lengkap, lalu menyatukannya kembali melalui *merge* atau mengakhirinya pada *activity final node* yang jelas (**Indikator 4.2**).
3. Menggunakan pasangan *fork* dan *join* untuk memodelkan dua proses yang berjalan secara paralel serta menyatukannya kembali sebelum alur dilanjutkan (**Indikator 4.2**).
4. Mengelompokkan setiap *action* ke dalam *swimlane* (partisi aktivitas) yang sesuai dengan aktor pelaku pada tabel skenario (**Indikator 4.1 & 4.2**).
5. Melakukan penelusuran (*traceability*) setiap *action* pada diagram ke tabel skenario Pertemuan 5 dan memverifikasi kelengkapan berkas menggunakan *checklist* penilaian resmi sebelum pengumpulan.

---

## 3. Dasar Teori & Prinsip Praktikum

### A. Sembilan Unsur Utama Activity Diagram (OMG UML 2.5.1)
1. **Initial Node:** Titik awal alur (tepat satu pada setiap diagram).
2. **Action:** Satu langkah kegiatan dari tabel skenario, ditulis dengan pola **Kata Kerja + Objek** (contoh: *Mengisi formulir pengajuan peminjaman*).
3. **Control Flow:** Garis panah yang menunjukkan urutan transisi antar-aktivitas.
4. **Decision:** Titik percabangan bersyarat; setiap jalur keluar wajib memiliki label *guard* dalam kurung siku (`[...]`).
5. **Merge:** Titik penggabungan kembali jalur percabangan menuju alur utama.
6. **Fork:** Batang pemecah satu alur menjadi dua atau lebih aktivitas paralel.
7. **Join:** Batang penyatu kembali aktivitas paralel dari *fork* (menunggu seluruh jalur paralel selesai sebelum berlanjut).
8. **Activity Final Node:** Titik akhir seluruh alur aktivitas.
9. **Swimlane (Partisi Aktivitas):** Pembagian kolom tanggung jawab berdasarkan aktor manusia maupun **Sistem**.

### B. Pemetaan Tabel Skenario (P05) ke Activity Diagram (P06)

| Unsur pada Tabel Skenario (P05) | Representasi pada Activity Diagram (P06) |
| :--- | :--- |
| **Skenario Normal** | Alur utama: rangkaian *action* dari *initial node* hingga *activity final node*. |
| **Skenario Alternative** | Cabang *decision* dengan *guard* spesifik (contoh: `[tersedia]` / `[tidak tersedia]`). |
| **Langkah `<<include>>`** | *Action* wajib pada alur utama sesuai urutan langkahnya (misal: *Periksa Ketersediaan* dari `LAB-UC04`). |
| **Langkah `<<extend>>`** | Cabang *decision* bersyarat sesuai *extension point* (misal: `[ya, memilih cetak]` menuju *Cetak Bukti Pengajuan* dari `LAB-UC05`). |
| **Kolom Kegiatan (Aktor)** | *Action* ditempatkan pada *swimlane* aktor manusia terkait. |
| **Kolom Respon Sistem** | *Action* ditempatkan pada *swimlane* **Sistem**. |
| **Dua Pemeriksaan Independen** | Pasangan **Fork** dan **Join** untuk eksekusi paralel sebelum pengambilan keputusan akhir. |
| **Collaboration** | **Tidak digambar** sebagai *action* maupun *swimlane* karena bukan urutan kegiatan. |

---

## 4. Hasil Praktikum

### A. Pemodelan 7 Activity Diagram Studi Kasus Laboratorium (`LAB`)
Seluruh 7 *use case* utama pada sistem `LabAlat` telah dimodelkan ke dalam format `.drawio` dan `.png` pada direktori `04_model_analisis/P06/LAB/`:

1. **`LAB-UC01` Lihat Ketersediaan Peralatan (`P06_2406072_LAB_activity_lihat_ketersediaan_v01`)**
   * **Swimlane:** Peminjam, Sistem.
   * **Alur & Logika:** Alur baca tanpa perubahan data, dilengkapi *decision* `Peralatan tersedia?` dengan *guard* `[tersedia]` dan `[tidak tersedia]` yang bertemu kembali pada *merge* sebelum berakhir.
2. **`LAB-UC02` Kelola Data Peralatan (`P06_2406072_LAB_activity_kelola_data_v01`)**
   * **Swimlane:** Petugas Laboratorium, Sistem.
   * **Alur & Logika:** Mengintegrasikan 3 *use case* varian ke dalam satu *decision* `Bentuk pengelolaan yang dipilih?`:
     * `[tambah]` $\rightarrow$ langkah pembeda `LAB-UC08` (Tambah Data Peralatan).
     * `[ubah]` $\rightarrow$ langkah pembeda `LAB-UC09` (Ubah Data Peralatan) + validasi `Data peralatan ditemukan?`.
     * `[hapus]` $\rightarrow$ langkah pembeda `LAB-UC10` (Hapus Data Peralatan) + validasi `Syarat penghapusan terpenuhi?` (tidak sedang dipinjam & tidak ada pengajuan aktif).
     * Ketiga cabang digabungkan oleh *merge* menuju validasi akhir `Data lengkap dan sah?`.
3. **`LAB-UC03` Ajukan Peminjaman (`P06_2406072_LAB_activity_peminjaman_v01`)**
   * **Swimlane:** Mahasiswa, Sistem, Petugas Laboratorium.
   * **Alur & Logika:** Memuat langkah wajib `<<include>>` *Periksa Ketersediaan (dari LAB-UC04)*, percabangan ketersediaan alat (`[tersedia]` vs `[tidak tersedia]`), serta percabangan `<<extend>>` pada akhir proses (`Mahasiswa memilih cetak bukti?` dengan *guard* `[ya, memilih cetak]` dan `[tidak]`).
4. **`LAB-UC05` Cetak Bukti Pengajuan (`P06_2406072_LAB_activity_cetak_bukti_v01`)**
   * **Swimlane:** Mahasiswa, Sistem.
   * **Alur & Logika:** Dimulai langsung pada *extension point* **Bukti pengajuan tersedia** (setelah status pengajuan tercatat *Menunggu Keputusan*). Memodelkan kondisi `[ya, memilih cetak]` hingga pencetakan bukti dan `[tidak]` untuk menutup konfirmasi tanpa mencetak.
5. **`LAB-UC06` Proses Keputusan Peminjaman (`P06_2406072_LAB_activity_keputusan_v01`) — *Tugas Mandiri***
   * **Swimlane:** Petugas Laboratorium, Sistem *(Mahasiswa tidak dilibatkan karena tidak memiliki langkah pada skenario)*.
   * **Alur & Logika:** Dikerjakan secara mandiri terlebih dahulu sebelum pencocokan pembanding. Memuat dua *decision* berurutan: `Pengajuan dapat diproses?` (`[dapat diproses]` / `[tidak dapat diproses]`) dan `Pengajuan disetujui?` (`[disetujui]` / `[ditolak]`) yang memperbarui status pengajuan secara eksplisit.
6. **`LAB-UC11` Catat Pengembalian Peralatan (`P06_2406072_LAB_activity_pengembalian_v01`)**
   * **Swimlane:** Mahasiswa, Sistem, Petugas Laboratorium.
   * **Alur & Logika:** Menggunakan pasangan **Fork** dan **Join** pada *swimlane* Petugas Laboratorium untuk memodelkan dua pemeriksaan paralel: *Periksa Kondisi Peralatan (dari LAB-UC12): kondisi fisik* dan *Periksa kelengkapan aksesori peralatan (unsur proses baru)*. Setelah *join*, *decision* `Kondisi peralatan baik dan lengkap?` memisahkan jalur `[baik dan lengkap]` (status alat kembali tersedia) dan `[rusak atau tidak lengkap]` (pencatatan kerusakan & jadwal perbaikan).
7. **`LAB-UC07` Lihat Laporan Peminjaman (`P06_2406072_LAB_activity_laporan_v01`)**
   * **Swimlane:** Kepala Laboratorium, Sistem.
   * **Alur & Logika:** Satu-satunya diagram yang melibatkan aktor Kepala Laboratorium. Dibatasi secara ketat pada pemilihan periode laporan dan pengecekan *decision* `Ada data peminjaman?` (`[ada]` / `[tidak ada]`).

### B. Pemodelan Tugas Sistem Informasi Akademik (`SIA`)
* **Berkas:** `04_model_analisis/P06/SIA/P06_2406072_SIA_activity_v01.drawio` (beserta `.png`)
* **Cakupan Proses:** Alur terpadu dari **Input Nilai Mata Kuliah (`SIA-UC08`)** hingga **Lihat KHS (`SIA-UC09`)**.
* **Struktur Swimlane (4 Partisi):** Dosen, Sistem, Admin Akademik, Mahasiswa.
* **Kontrol Alur Utama:**
  * *Decision* kelengkapan nilai (`Nilai sudah lengkap?`): *guard* `[belum lengkap]` mengembalikan alur ke Dosen untuk melengkapi nilai dan digabungkan kembali melalui *merge* menuju pengesahan Admin Akademik.
  * Pasangan *Fork & Join*: Setelah nilai disahkan dan Sistem menyiapkan publikasi hasil studi, alur dipecah secara paralel menjadi *Menerbitkan KHS pada portal akademik* dan *Mengirim pemberitahuan hasil studi kepada mahasiswa*, lalu disatukan oleh *join* sebelum Mahasiswa menjalankan *Melihat KHS*.

### C. Pemetaan Struktur Direktori Repositori (`IFRWP5149_2406072_LabAlat`)
```text
IFRWP5149_2406072_LabAlat/
├── 01_skenario/
│   ├── P05_2406072_LAB_telaah_skenario_v01.docx      (Tetap, tidak diubah)
│   └── P05_2406072_SIA_skenario_v01.docx             (Tetap, tidak diubah)
├── 03_latihan_tools/                                 (Tetap, dari P01-P02)
├── 04_model_analisis/
│   ├── P03/                                          (Tetap, jangan diubah)
│   ├── P04/                                          (Tetap, jangan diubah)
│   └── P06/
│       ├── LAB/
│       │   ├── P06_2406072_LAB_activity_lihat_ketersediaan_v01.drawio & .png
│       │   ├── P06_2406072_LAB_activity_kelola_data_v01.drawio & .png
│       │   ├── P06_2406072_LAB_activity_peminjaman_v01.drawio & .png
│       │   ├── P06_2406072_LAB_activity_cetak_bukti_v01.drawio & .png
│       │   ├── P06_2406072_LAB_activity_keputusan_v01.drawio & .png
│       │   ├── P06_2406072_LAB_activity_pengembalian_v01.drawio & .png
│       │   └── P06_2406072_LAB_activity_laporan_v01.drawio & .png
│       └── SIA/
│           └── P06_2406072_SIA_activity_v01.drawio & .png
├── 05_model_desain/                                  (Tetap kosong)
└── 06_Laporan/
    ├── P05_2406072_jobsheet_review_v01.md
    └── P06_2406072_jobsheet_review_v01.md            <-- (Berkas ini)
```

---

## 5. Analisis & Verifikasi Checklist Penilaian

1. **Keterlacakan (*Traceability*) & Konsistensi Artefak:**
   * Seluruh 7 diagram `LAB` dan 1 diagram `SIA` memiliki tepat satu *initial node* dan satu *activity final node*, tanpa adanya *action* yang menggantung (*dangling*).
   * Use case pendukung (`LAB-UC04`, `LAB-UC12`) dan varian CRUD (`LAB-UC08`, `LAB-UC09`, `LAB-UC10`) tidak dibuatkan file terpisah, melainkan terintegrasi sebagai *action* `<<include>>` dan cabang *decision* pada diagram induknya sesuai aturan jobsheet.
   * Elemen tambahan pada `LAB-UC11` (*Periksa kelengkapan aksesori peralatan*) telah diberi label keterangan **unsur proses baru** agar tidak rancu dengan kebutuhan P03–P05.

2. **Catatan Evaluasi Tugas Mandiri (`LAB-UC06` Proses Keputusan Peminjaman):**
   * **Perbandingan Awal:** Pada rancangan mandiri sebelum membuka lampiran pembanding, validasi status pengajuan hanya berfokus pada pilihan setuju/tolak oleh Petugas Laboratorium.
   * **Perbaikan Pasca-Review:** Setelah mencocokkan dengan *checklist* C.4 dan berkas pembanding, ditambahkan *decision* awal `Pengajuan dapat diproses?` dengan *guard* `[tidak dapat diproses]` untuk menangani kasus data pengajuan yang sudah dibatalkan atau berubah status sebelum sempat diproses petugas, sehingga seluruh kemungkinan kondisi tertutup sempurna.

---

## 6. Kesimpulan
Transformasi dari tabel skenario *use case* (Pertemuan 5) menjadi *Activity Diagram* (Pertemuan 6) memberikan visualisasi alur kontrol yang presisi, pembagian tanggung jawab antar-aktor melalui *swimlane*, serta mekanisme percabangan (*decision/merge*) dan konkurensi (*fork/join*) sesuai standar OMG UML 2.5.1. Seluruh berkas `.drawio` dan ekspor `.png` versi `v01` telah diverifikasi menggunakan *checklist* penilaian serta tersusun rapi di dalam repositori `IFRWP5149_2406072_LabAlat`.