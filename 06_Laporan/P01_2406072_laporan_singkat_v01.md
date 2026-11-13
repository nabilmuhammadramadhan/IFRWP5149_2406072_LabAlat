# Evaluasi Kesesuaian Repositori Pertemuan 1 (`IFRWP5149_2406072_LabAlat`)

Dokumen ini berisi hasil audit objektif terhadap struktur folder, penamaan berkas, dan kelengkapan artefak **Pertemuan 1** pada repositori **`IFRWP5149_2406072_LabAlat`** berdasarkan SOP di Modul Praktikum Pertemuan 1.

---

## 1. Identitas & Struktur Folder Induk

* **Nama Folder Induk:** `IFRWP5149_2406072_LabAlat` — **Sudah sesuai** dengan pola wajib `IFRWP5149_<NIM>_LabAlat`.
* **Penamaan Subfolder:** Pada repositori digunakan huruf kapital di awal kata (`00_Administrasi`, `01_Skenario`, `02_Template`, `03_Latihan_Tools`, `04_Model_Analisis`, `05_Model_Desain`, `06_Laporan`), sedangkan pada SOP modul ditulis menggunakan huruf kecil semua (`00_administrasi`, dst.). 
  * *Catatan:* Pada sistem operasi Windows yang bersifat *case-insensitive*, penamaan ini aman. Namun, jika dikumpulkan ke sistem berbasis Linux atau diperiksa menggunakan skrip otomatis (*automated script*), perbedaan kapitalisasi ini berpotensi menyebabkan berkas tidak terbaca.

---

## 2. Audit Kelengkapan & Penamaan Artefak Pertemuan 1

| Folder | Ketentuan Modul (SOP P01) | Kondisi di Repositori Saat Ini | Status & Solusi |
| :--- | :--- | :--- | :--- |
| **Root** | `README.md` | `README.md` ada | **Sesuai.** Pastikan isinya memuat identitas (Nabil Muhammad Ramadhan / `2406072`), studi kasus LabAlat, kakas `draw.io`, daftar isi, dan status progres P01. |
| **`00_Administrasi`** | `P01_2406072_logbook_v01.md` | `P01_2406072_logbook_v01.md` ada | **Sesuai.** |
| **`01_Skenario`** | `S-ORI-01_orientasi_kasus_v01.md` | `S-ORI-01_orientasi_kasus_v01.md` ada | **Sesuai.** |
| **`02_Template`** | `template_metadata_artefak_v01.md` | `template_metadata_artefak__v01.md` *(terdapat dua garis bawah `__`)* | **Kurang tepat (Typo penamaan).** Hapus satu garis bawah menjadi `template_metadata_artefak_v01.md`. |
| **`03_Latihan_Tools`** | Langsung di dalam `03_latihan_tools/`:<br>- `P01_2406072_latihan_activity_v01.drawio`<br>- `P01_2406072_latihan_activity_v01.png` | Diletakkan di dalam subfolder `/P01/` dan nama berkas ekspornya menjadi `P01_2406072_latihan_activity_v01.drawio.png` | **Kurang tepat (2 temuan):**<br>1. Modul mencontohkan berkas diletakkan langsung di `03_latihan_tools` (meski pemisahan subfolder `/P01` secara organisasi cukup rapi karena repositori sudah berjalan hingga P06).<br>2. **Ekstensi ganda** (`.drawio.png`). Ubah menjadi `P01_2406072_latihan_activity_v01.png`. |
| **`04_Model_Analisis` & `05_Model_Desain`** | Kosong pada tahap P01 | Sudah terisi artefak P03–P06 (serta terdapat berkas *dummy* `tes.md` di `05_Model_Desain`) | **Wajar** karena repositori sudah lanjut hingga Pertemuan 6. Namun, segera hapus berkas `tes.md` di `05_Model_Desain` agar folder bersih dari berkas uji coba. |
| **`06_Laporan`** | `P01_2406072_laporan_singkat_v01.md` | `P01_2406072_laporan_singkat_v01.md` ada | **Sesuai.** |

---

## 3. Checklist Tindakan Perbaikan Khusus Modul 1

Berikut adalah daftar periksa (*checklist*) untuk memastikan seluruh artefak Pertemuan 1 mematuhi aturan modul 100%:

- [ ] **Perbaiki typo nama template di `02_Template/`:**
  * Ubah `template_metadata_artefak__v01.md` $\rightarrow$ `template_metadata_artefak_v01.md`.
- [ ] **Perbaiki ekstensi ganda pada gambar ekspor di `03_Latihan_Tools/P01/`:**
  * Ubah `P01_2406072_latihan_activity_v01.drawio.png` $\rightarrow$ `P01_2406072_latihan_activity_v01.png`.
- [ ] **Bersihkan berkas sampah di `05_Model_Desain/`:**
  * Hapus berkas `tes.md`.
- [ ] **Verifikasi isi diagram `P01_2406072_latihan_activity_v01.drawio`:**
  * Pastikan hanya memuat tepat 4 elemen berurutan: *Initial Node* $\rightarrow$ *Buka daftar peralatan* $\rightarrow$ *Lihat informasi ketersediaan* $\rightarrow$ *Activity Final Node*.
  * Pastikan terdapat judul kanvas **Latihan kakas S-ORI-01** dan catatan status **Belum divalidasi sebagai model proses** tanpa tambahan *swimlane* atau percabangan.
- [ ] **Verifikasi kelengkapan isi dokumen teks P01:**
  * Pastikan `P01_2406072_logbook_v01.md` dan `P01_2406072_laporan_singkat_v01.md` sudah terisi catatan kakas (`draw.io`), bukti uji buka ulang berkas `.drawio`, serta jawaban pertanyaan orientasi kasus.