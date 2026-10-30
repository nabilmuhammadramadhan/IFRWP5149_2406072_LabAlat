<!-- skenario  -->
Studi kasus ini memakai diagram kumulatif Pertemuan 4 sebagai acuan.
Kebutuhan LAB-R01 sampai LAB-R11 dan spesifikasi 17 hubungan pada
diagram dirujuk dari Jobsheet Pertemuan 4 (khususnya Tabel 4.5); tidak ada
kebutuhan baru dan tidak ada use case baru pada pertemuan ini. Seluruh
tabel skenario studi kasus dimuat lengkap pada bagian ini sebagai bahan
kajian, sehingga mahasiswa tidak lagi ditugasi menulis tabel studi kasus.
Pekerjaan mahasiswa pada studi kasus adalah menelaah kedua belas tabel
tersebut terhadap diagram acuan.

<!--  Indeks tabel skenario studi kasus LAB -->
|   ID   |        Nama_use_case        |
|--------|-----------------------------|
|LAB-UC01|Lihat Ketersediaan Peralatan |
|LAB-UC03|      Ajukan Peminjaman      |
|LAB-UC04|    Periksa Ketersediaan     |
|LAB-UC05|    Cetak Bukti Pengajuan    |
|LAB-UC02|    Kelola Data Peralatan    |
|LAB-UC08|    Tambah Data Peralatan    |
|LAB-UC09|     Ubah Data Peralatan     |
|LAB-UC10|    Hapus Data Peralatan     |
|LAB-UC06| Proses Keputusan Peminjaman |
|LAB-UC07|  Lihat Laporan Peminjaman   |
|LAB-UC11|Catat Pengembalian Peralatan |
|LAB-UC12|  Periksa Kondisi Peralatan  |


|           Tabel_skenario            |                           Relasi_yang_ditelusur                            |  Hasil_pencocokan   |Checklist_C.4 |
|-------------------------------------|----------------------------------------------------------------------------|---------------------|--------------|
|LAB-UC01_Lihat_Ketersediaan_Peralatan|                            Asosiasi_(Peminjam)                             |Sesuai_dengan_diagram|  Terpenuhi   |
|     LAB-UC03_Ajukan_Peminjaman      |Asosiasi_(Peminjam),Include(LAB-UC04),Extend(LAB-UC05),Realization(LAB-CO01)|Sesuai_dengan_diagram|  Terpenuhi   |
|    LAB-UC04_Periksa_Ketersediaan    |                          Include_(dari_LAB-UC03)                           |Sesuai_dengan_diagram|  Terpenuhi   |
|   LAB-UC05_Cetak_Bukti_Pengajuan    |              Asosiasi_khusus_(Mahasiswa),Extend(ke_LAB-UC03)               |Sesuai_dengan_diagram|  Terpenuhi   |
|   LAB-UC02_Kelola_Data_Peralatan    |       Asosiasi_(Petugas_Laboratorium),Generalization(use_case_umum)        |Sesuai_dengan_diagram|  Terpenuhi   |
|   LAB-UC08_Tambah_Data_Peralatan    |                       Generalization_(dari_LAB-UC02)                       |Sesuai_dengan_diagram|  Terpenuhi   |
|    LAB-UC09_Ubah_Data_Peralatan     |                       Generalization_(dari_LAB-UC02)                       |Sesuai_dengan_diagram|  Terpenuhi   |
|    LAB-UC10_Hapus_Data_Peralatan    |                       Generalization_(dari_LAB-UC02)                       |Sesuai_dengan_diagram|  Terpenuhi   |
|LAB-UC06_Proses_Keputusan_Peminjaman |                      Asosiasi_(Petugas_Laboratorium)                       |Sesuai_dengan_diagram|  Terpenuhi   |
|  LAB-UC07_Lihat_Laporan_Peminjaman  |              Asosiasi_(Kepala_Laboratorium)_-_Berdiri_sendiri              |Sesuai_dengan_diagram|  Terpenuhi   |
|LAB-UC11_Catat_Pengembalian_Peralatan|  Asosiasi_(Petugas_Laboratorium),Include(LAB-UC12),Realization(LAB-CO02)   |Sesuai_dengan_diagram|  Terpenuhi   |
| LAB-UC12_Periksa_Kondisi_Peralatan  |                          Include_(dari_LAB-UC11)                           |Sesuai_dengan_diagram|  Terpenuhi   |
 

 