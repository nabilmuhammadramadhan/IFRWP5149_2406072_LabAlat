# JOBSHEET REVIEW PRAKTIKUM PERTEMUAN 5

**Skenario Use Case: Dari Diagram ke Langkah Kegiatan**

## 1. Identitas & Metadata Praktikum

* **Nama Mahasiswa:** Nabil Muhammad Ramadhan

* **NIM:** 2406072

* **Mata Kuliah:** Rekayasa Perangkat Lunak (Praktikum)

* **Pertemuan:** 5 (Skenario Use Case)

* **Repositori GitHub:** `IFRWP5149_2406072_LabAlat`

* **Lokasi Penyimpanan Berkas:** `06_Laporan/P05_2406072_jobsheet_review_v01.md`

## 2. Tujuan Pembelajaran

Setelah menyelesaikan praktikum pertemuan ke-5 ini, mahasiswa mampu:

1. Menerjemahkan model visual *Use Case Diagram* menjadi spesifikasi kebutuhan tekstual berbentuk tabel skenario (*Use Case Scenario*).

2. Menyusun urutan interaksi antara aktor dan sistem secara logis berdasarkan alur normal (*Basic Flow*) serta mengantisipasi jalur alternatif dan pengecualian (*Alternative/Exception Flow*).

3. Memetakan lima jenis relasi pada *Use Case Diagram* (*Association*, *Generalization*, *Include*, *Extend*, dan *Collaboration*) ke dalam struktur tabel skenario secara konsisten.

## 3. Dasar Teori & Prinsip Praktikum

### A. Struktur Tabel Skenario Use Case

Setiap *use case* yang digambarkan pada diagram dijabarkan ke dalam komponen standar berikut:

* **Kode & Nama Use Case:** Identitas unik yang merujuk langsung pada diagram (misal: `UC-01`).

* **Aktor:** Entitas utama (*Primary Actor*) dan pendukung (*Secondary Actor*) yang berinteraksi.

* **Deskripsi Singkat:** Ringkasan tujuan fungsional dari *use case* tersebut.

* **Pre-Condition:** Kondisi awal yang wajib terpenuhi sebelum skenario dijalankan.

* **Basic Flow (Alur Utama):** Langkah-langkah interaksi normal antara aktor dan sistem hingga tujuan tercapai.

* **Alternative / Exception Flow:** Penanganan apabila terjadi percabangan kondisi, kesalahan input, atau kegagalan validasi.

* **Post-Condition:** Status akhir sistem setelah *use case* selesai dieksekusi.

### B. Kaidah Penulisan Langkah Interaksi

* Menggunakan kalimat aktif berstruktur **Subjek + Predikat + Objek** (contoh: *"Mahasiswa menekan tombol Simpan"* atau *"Sistem memvalidasi ketersediaan stok"*).

* Memisahkan aksi yang dilakukan oleh **Aktor** dengan respons yang diproses oleh **Sistem** secara berurutan.

* Menghindari istilah teknis implementasi tingkat rendah (seperti nama tabel database atau tipe variabel) pada tahap analisis kebutuhan.

### C. Pemetaan 5 Relasi Diagram ke Tabel Skenario

| Jenis Relasi | Representasi pada Diagram | Implementasi pada Tabel Skenario | 
| ----- | ----- | ----- | 
| **1. Association** | Garis lurus penghubung Aktor dengan Use Case. | Aktor dicantumkan pada kolom **Aktor** dan menjadi subjek pemicu langkah pertama pada *Basic Flow*. | 
| **2. Generalization** | Garis panah tertutup (segitiga kosong) antar-use case/aktor. | *Use case* anak mewarisi alur dasar dari *use case* induk, lalu menambahkan langkah spesifiknya sendiri. | 
| **3. Include (`<<include>>`)** | Panah putus-putus dari *base* ke *included use case*. | Pada *Basic Flow* tertulis pemanggilan eksplisit (misal: *"Sistem menjalankan use case Validasi Login (`UC-00`)"*). | 
| **4. Extend (`<<extend>>`)** | Panah putus-putus dari *extension* ke *base use case*. | Ditempatkan pada bagian **Alternative Flow** disertai *extension point* (syarat kondisi pemicunya). | 
| **5. Collaboration** | Interaksi multi-aktor dalam satu rangkaian proses bisnis. | Melibatkan aktor utama dan sekunder pada satu tabel skenario atau rangkaian *use case* yang saling terhubung. | 

## 4. Hasil Praktikum

### A. Penelaahan Skenario Studi Kasus Sistem Informasi Peminjaman Alat Laboratorium (12 Use Case)

Berdasarkan spesifikasi sistem `LabAlat`, seluruh kebutuhan fungsional telah dijabarkan ke dalam 12 dokumen skenario yang mencakup siklus pengelolaan alat:

 1. **`UC-01` Login Sistem:** Autentikasi pengguna (Mahasiswa, Dosen, Laboran) menggunakan NIM/NIP dan kata sandi.

 2. **`UC-02` Kelola Data Alat (CRUD):** Penambahan, pembaruan spesifikasi, dan penghapusan data inventaris alat oleh Laboran.

 3. **`UC-03` Pencarian & Cek Ketersediaan Alat:** Penelusuran katalog alat beserta status ketersediaan stok secara *real-time*.

 4. **`UC-04` Pengajuan Peminjaman Alat:** Pengisian formulir peminjaman, pemilihan jadwal, dan penentuan jumlah unit oleh Peminjam.

 5. **`UC-05` Validasi & Persetujuan Peminjaman:** Pemeriksaan kelayakan dan persetujuan pengajuan oleh Laboran (*collaboration* dengan Peminjam).

 6. **`UC-06` Penolakan Peminjaman:** Penanganan *exception/extend* apabila stok tidak mencukupi atau syarat peminjaman tidak terpenuhi.

 7. **`UC-07` Serah Terima Pengambilan Alat:** Pencatatan kondisi awal alat dan perubahan status menjadi *Dipinjam*.

 8. **`UC-08` Pengajuan Perpanjangan Waktu:** Permintaan penambahan durasi pinjam sebelum batas waktu berakhir (`<<extend>>` dari peminjaman aktif).

 9. **`UC-09` Pengembalian Alat:** Proses penyerahan kembali alat oleh Peminjam kepada Laboran.

10. **`UC-10` Pengecekan Kondisi & Denda:** Pemeriksaan fisik alat pasca-kembali serta kalkulasi denda jika terlambat atau rusak (`<<include>>` pada pengembalian).

11. **`UC-11` Pelaporan Kerusakan Alat:** Pencatatan insiden kerusakan saat penggunaan berlangsung untuk penjadwalan perbaikan.

12. **`UC-12` Pembuatan Laporan Peminjaman & Inventaris:** Rekapitulasi riwayat transaksi dan kondisi aset laboratorium secara periodik.

### B. Penyusunan Skenario Tugas Sistem Informasi Akademik / SIA (7 Use Case)

Sebagai latihan mandiri pemetaan diagram ke skenario, disusun 7 rancangan skenario utama pada domain SIA:

1. **`SIA-01` Autentikasi Pengguna:** Validasi hak akses Mahasiswa, Dosen Wali, dan Admin Akademik.

2. **`SIA-02` Pengisian Kartu Rencana Studi (KRS):** Pemilihan mata kuliah sesuai kuota SKS dan prasyarat nilai.

3. **`SIA-03` Perwalian & Persetujuan KRS:** Peninjauan dan validasi KRS mahasiswa oleh Dosen Wali.

4. **`SIA-04` Perubahan Rencana Studi (PRS):** Penambahan atau pembatalan mata kuliah pada masa revisi (`<<extend>>` dari pengisian KRS).

5. **`SIA-05` Input Nilai Mahasiswa:** Pengisian komponen nilai (Tugas, UTS, UAS) oleh Dosen Pengampu.

6. **`SIA-06` Penerbitan Kartu Hasil Studi (KHS):** Kalkulasi otomatis Indeks Prestasi Semester (IPS) dan IPK setelah nilai tervalidasi.

7. **`SIA-07` Cetak Transkrip Nilai Sementara:** Pengunduhan dokumen rekapitulasi nilai akademik dalam format PDF.

### C. Pemetaan Struktur Direktori & Deliverable Repositori (`IFRWP5149_2406072_LabAlat`)

```
IFRWP5149_2406072_LabAlat/
├── 01_Proposal/
├── 02_Kebutuhan/
├── 03_UseCase_Diagram/
│   └── P04_2406072_usecase_diagram_labalat.puml / .png
├── 04_UseCase_Scenario/
│   ├── P05_2406072_skenario_labalat_uc01_uc12.md
│   └── P05_2406072_skenario_sia_uc01_uc07.md
├── 05_Wireframe_UI/
└── 06_Laporan/
    ├── P04_2406072_jobsheet_review_v01.md
    └── P05_2406072_jobsheet_review_v01.md   <-- (Berkas ini)

```

## 5. Analisis

1. **Ketepatan Pemetaan Relasi:**

   * Relasi `<<include>>` pada aktivitas autentikasi (`UC-01`) dan pengecekan kondisi alat (`UC-10`) berhasil memastikan tidak adanya duplikasi langkah yang berulang di setiap tabel skenario.

   * Relasi `<<extend>>` pada pengajuan perpanjangan (`UC-08`) dan penolakan peminjaman (`UC-06`) ditempatkan secara akurat pada bagian *Alternative Flow* sehingga alur utama (*Basic Flow*) tetap fokus pada kondisi sukses (*happy path*).

   * Relasi *Collaboration* antara aktor Peminjam dan Laboran terlihat jelas pada siklus `UC-04` hingga `UC-07`, di mana *Post-Condition* dari pengajuan menjadi *Pre-Condition* bagi proses validasi.

2. **Konsistensi Antara Diagram (P04) dan Skenario (P05):**

   * Seluruh nama *use case* dan peran aktor pada dokumen skenario telah disinkronkan 100% dengan *Use Case Diagram* yang dikerjakan pada Pertemuan 4 (`03_UseCase_Diagram`), sehingga keterlacakan kebutuhan (*requirements traceability*) terjaga dengan baik menuju tahap perancangan antarmuka (*wireframe*) maupun diagram perilaku berikutnya (*Activity* & *Sequence Diagram*).

## 6. Kesimpulan

Penyusunan skenario *use case* menjembatani representasi visual pada *Use Case Diagram* dengan spesifikasi perilaku sistem yang terukur. Melalui penerapan struktur tabel skenario yang baku dan pemetaan lima relasi utama (*Association*, *Generalization*, *Include*, *Extend*, dan *Collaboration*), setiap alur normal maupun pengecualian pada sistem `LabAlat` dan `SIA` dapat terdokumentasi secara sistematis, konsisten, dan siap digunakan sebagai acuan tahap perancangan perangkat lunak berikutnya.