# Evaluasi Kesesuaian Repositori Pertemuan 2 (`IFRWP5149_2406072_LabAlat`)

Dokumen ini berisi hasil audit objektif terhadap struktur folder, penamaan berkas, dan kelengkapan artefak **Pertemuan 2** pada repositori **`IFRWP5149_2406072_LabAlat`** berdasarkan SOP di Modul Praktikum Pertemuan 2.

---

## 1. Audit Kelengkapan & Penamaan Artefak Pertemuan 2

| Folder | Ketentuan Modul (SOP P02) | Kondisi di Repositori Saat Ini | Status & Solusi |
| :--- | :--- | :--- | :--- |
| **`00_Administrasi`** | `P02_2406072_logbook_v01.md` | `P02_2406072_logbook_v01.md` ada | **Sesuai.** |
| **`01_Skenario`** | • `P02_LAB_skenario_v01.md`<br>• `P02_SIA_skenario_v01.md` | Keduanya ada | **Sesuai.** |
| **`03_Latihan_Tools/P02/LAB`** | • `P02_2406072_LAB_notasi_usecase_v01.drawio`<br>• `P02_2406072_LAB_notasi_usecase_v01.png` | • `P02_2406072_LAB_notasi_usecase_v01.drawio`<br>• `P02_2406072_LAB_notasi_usecase_v01.drawio.png` | **Kurang tepat pada berkas ekspor.** Terdapat ekstensi ganda (`.drawio.png`). Ubah menjadi `P02_2406072_LAB_notasi_usecase_v01.png`. |
| **`03_Latihan_Tools/P02/SIA`** | 1. Diagram keliru awal:<br>• `P02_2406072_SIA_perbaikan_notasi_v01.drawio`<br>• *(opsional ekspor `.png`)*<br><br>2. Diagram hasil perbaikan:<br>• `P02_2406072_SIA_notasi_v01.drawio`<br>• `P02_2406072_SIA_notasi_v01.png` | • `P02_2406072_SIA_notasi_v01.drawio`<br>• `P02_2406072_SIA_notasi_v01.drawio.png`<br>• `P02_2406072_SIA_perbaikan_notasi_v01.drawio`<br>• `P02_2406072_SIA_perbaikan_notasi_v01.drawio.png` | **Kurang tepat pada ekstensi berkas ekspor.** Hapus `.drawio` pada nama berkas gambar agar menjadi `P02_2406072_SIA_notasi_v01.png` dan `P02_2406072_SIA_perbaikan_notasi_v01.png`. |
| **`06_Laporan`** | `P02_2406072_jobsheet_review_v01.md` | `P02_2406072_jobsheet_review_v01.md` ada | **Sesuai.** |

---

## 2. Checklist Verifikasi Isi Artefak Pertemuan 2

Secara struktur dan keberadaan berkas, artefak Pertemuan 2 sudah lengkap. Silakan lakukan 2 langkah pembersihan dan pengecekan konten berikut:

1. **Perbaiki ekstensi ganda di `03_Latihan_Tools/P02/`:**
   * `LAB/P02_2406072_LAB_notasi_usecase_v01.drawio.png` $\rightarrow$ `P02_2406072_LAB_notasi_usecase_v01.png`
   * `SIA/P02_2406072_SIA_notasi_v01.drawio.png` $\rightarrow$ `P02_2406072_SIA_notasi_v01.png`
   * `SIA/P02_2406072_SIA_perbaikan_notasi_v01.drawio.png` $\rightarrow$ `P02_2406072_SIA_perbaikan_notasi_v01.png`

2. **Audit kesesuaian isi diagram & laporan (sesuai checklist modul):**
   * **Kasus `LAB`:** Pastikan judul sistem adalah *Sistem Informasi Peminjaman dan Pengembalian Peralatan Laboratorium Kampus*, aktor *Mahasiswa* dan *Petugas laboratorium* berada di luar kotak batas sistem, serta tidak ada panah urutan antar *use case* (*Lihat ketersediaan peralatan* dan *Kelola data peralatan*).
   * **Kasus `SIA` (Awal vs Perbaikan):**
     * Berkas `perbaikan_notasi_v01` memuat label status **DIAGRAM AWAL UNTUK KOREKSI** dan menampilkan 4 kesalahan yang disengaja (aktor di dalam batas sistem, *use case* berbentuk kotak biasa, relasi silang aktor ke fungsi yang salah, dan judul sistem laboratorium).
     * Berkas `notasi_v01` sudah mengoreksi keempatnya dengan judul *Sistem Informasi Akademik*, aktor *Mahasiswa* terhubung ke *Lihat jadwal kuliah*, dan *Admin akademik* terhubung ke *Kelola jadwal kuliah*.
   * **`P02_2406072_jobsheet_review_v01.md`:** Pastikan sudah memuat tabel 4 temuan kesalahan SIA, penjelasan mengapa garis asosiasi bukan alur proses (*sequence/flow*), serta hasil uji buka ulang berkas `.drawio`.