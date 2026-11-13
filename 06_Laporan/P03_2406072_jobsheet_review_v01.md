# Evaluasi Kesesuaian Repositori Pertemuan 3 (`IFRWP5149_2406072_LabAlat`)

Dokumen ini berisi hasil audit objektif terhadap struktur folder, penamaan berkas, dan kelengkapan artefak **Pertemuan 3** pada repositori **`IFRWP5149_2406072_LabAlat`** berdasarkan SOP di Modul Praktikum Pertemuan 3 (*Use Case Diagram dan Use Case Description*).

## 1. Audit Struktur & Penamaan Artefak Pertemuan 3

| Folder | Ketentuan Modul (SOP P03) | Kondisi di Repositori Saat Ini | Status & Solusi |
| :--- | :--- | :--- | :--- |
| **`00_Administrasi`** | `P03_2406072_logbook_v01.md` | `P03_2406072_logbook_v01.md` ada | **Sesuai.** |
| **`01_Skenario`** | - `P03_LAB_skenario_v01.md`<br>- `P03_SIA_skenario_v01.md`<br>*(Catatan: Langkah 1 modul juga menyebut `kebutuhan_v01.md`, namun Gambar 3.1 struktur resmi memasukkannya ke `skenario`)* | - `P03_LAB_skenario_v01.md` ada<br>- `P03_SIA_skenario_v01.md` ada | **Sesuai** dengan pohon direktori resmi modul. |
| **`03_Latihan_Tools/P03/LAB`** | - `P03_2406072_LAB_deskripsi_v01.md`<br>- `P03_2406072_LAB_usecase_v01.drawio`<br>- `P03_2406072_LAB_usecase_v01.png` | - `P03_2406072_LAB_deskripsi_v01.md`<br>- `P03_2406072_LAB_usecase_v01.drawio`<br>- `P03_2406072_LAB_usecase_v01.drawio.png` | **Kurang tepat pada file ekspor.** Hapus ekstensi ganda `.drawio.png` menjadi `P03_2406072_LAB_usecase_v01.png`. |
| **`03_Latihan_Tools/P03/SIA` vs `04_Model_Analisis`** | Terdapat **inkonsistensi internal** pada modul:<br>- Gambar 3.1 meletakkan artefak SIA di `03_latihan_tools/P03/SIA/`.<br>- Teks Langkah 6 (hal. 42) menginstruksikan membuat diagram SIA di `04_model_analisis/P03/SIA/`. | Ketiga berkas SIA (`deskripsi_v01.md`, `usecase_v01.drawio`, `usecase_v01.drawio.png`) tersimpan di `03_Latihan_Tools/P03/SIA/`, sedangkan di `04_Model_Analisis/` terdapat `P03_2406072_usecase_v01.drawio` & `.png`. | **Sudah tepat mengikuti Gambar 3.1** untuk folder latihan.<br>*Solusi:* Hapus ekstensi ganda `.drawio.png` menjadi `.png`, serta tambahkan kode kasus (`LAB` atau `SIA`) pada nama berkas di `04_Model_Analisis` agar tidak tertukar. |
| **`06_Laporan`** | `P03_2406072_jobsheet_review_v01.md` | `P03_2406072_jobsheet_review_v01.md` ada | **Sesuai.** |

---

## 2. Checklist Verifikasi Isi Artefak Pertemuan 3

### A. Perbaikan Nama Berkas Ekspor
* Ubah `03_Latihan_Tools/P03/LAB/P03_2406072_LAB_usecase_v01.drawio.png` $\rightarrow$ `P03_2406072_LAB_usecase_v01.png`
* Ubah `03_Latihan_Tools/P03/SIA/P03_2406072_SIA_usecase_v01.drawio.png` $\rightarrow$ `P03_2406072_SIA_usecase_v01.png`

### B. Audit Diagram & Deskripsi Kasus `LAB` (Studi Kasus Terbimbing)
* **3 Aktor:** *Mahasiswa*, *Petugas laboratorium*, dan *Kepala laboratorium* berada di luar batas sistem (*Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*).
* **7 Use Case di dalam batas sistem:**
  1. `LAB-UC01`: *Lihat ketersediaan peralatan* (Mahasiswa)
  2. `LAB-UC02`: *Kelola data peralatan* (Petugas laboratorium)
  3. `LAB-UC03`: *Ajukan peminjaman* (Mahasiswa)
  4. `LAB-UC04`: *Periksa ketersediaan* (Disertakan oleh UC03)
  5. `LAB-UC05`: *Cetak bukti pengajuan* (Tambahan bersyarat pada UC03, juga terhubung asosiasi ke Mahasiswa)
  6. `LAB-UC06`: *Proses keputusan peminjaman* (Petugas laboratorium)
  7. `LAB-UC07`: *Lihat laporan peminjaman* (Kepala laboratorium)
* **Relasi & Arah Panah:**
  * `Ajukan peminjaman` $\xrightarrow{\ll include \gg}$ `Periksa ketersediaan` (garis putus-putus dengan panah terbuka mengarah ke *Periksa ketersediaan*).
  * `Cetak bukti pengajuan` $\xrightarrow{\ll extend \gg}$ `Ajukan peminjaman` (garis putus-putus dengan panah terbuka mengarah ke *Ajukan peminjaman*, disertai catatan `condition: [mahasiswa memilih cetak]` dan `extension point: Bukti pengajuan tersedia`).
* **Deskripsi (`P03_2406072_LAB_deskripsi_v01.md`):** Memuat deskripsi lengkap minimal untuk *Ajukan peminjaman* (ID, sumber kebutuhan, tujuan, aktor, pemicu, prasyarat, alur utama, alur alternatif/pengecualian, pascakondisi berhasil & gagal, serta aturan bisnis/asumsi).

### C. Audit Diagram & Deskripsi Kasus `SIA` (Tugas Praktik)
* **Aktor:** Hanya *Mahasiswa* dan *Dosen wali* (tidak memasukkan *Admin akademik* dari Pertemuan 2 karena di luar skenario KRS).
* **Relasi:**
  * *Ajukan KRS* `<<include>>` *Validasi KRS*
  * *Unduh bukti pengajuan KRS* `<<extend>>` *Ajukan KRS* (lengkap dengan *extension point* dan kondisi).
* **4 Deskripsi Wajib (`P03_2406072_SIA_deskripsi_v01.md`):**
  1. *Ajukan KRS* (menyertakan alur alternatif validasi gagal & tambahan unduh bukti)
  2. *Validasi KRS*
  3. *Unduh bukti pengajuan KRS*
  4. *Proses keputusan KRS* (menjelaskan hasil persetujuan maupun penolakan beserta catatan)

### D. Laporan Review (`P03_2406072_jobsheet_review_v01.md`)
* Memuat alasan pemodelan `<<include>>` dan `<<extend>>` pada kasus `LAB` dan `SIA`.
* Memuat hasil uji konsistensi 3 situasi pada kasus `SIA`:
  1. Validasi berhasil dan mahasiswa tidak mengunduh bukti.
  2. Validasi gagal.
  3. Validasi berhasil dan mahasiswa memilih mengunduh bukti.
* Mencatat hasil uji buka ulang berkas `.drawio`.