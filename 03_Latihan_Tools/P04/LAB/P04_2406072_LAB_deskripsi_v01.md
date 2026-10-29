<!-- use case description baru -->
|       Elemen        |                                LAB-UC11:_Catat_Pengembalian_Peralatan                                |
|---------------------|------------------------------------------------------------------------------------------------------|
|     ID_dan_nama     |                                LAB-UC11:_Catat_Pengembalian_Peralatan                                |
|  Sumber_kebutuhan   |                                         LAB-R09_dan_LAB-R10                                          |
|       Tujuan        |             Pengembalian_tercatat_dan_status_peminjaman_serta_kondisi_peralatan_terbaru              |
|     Aktor_utama     |                                         Petugas_Laboratorium                                         |
|       Pemicu        |   Petugas_memilih_fungsi_pencatatan_pengembalian_dan_menentukan_peminjaman_yang_akan_dikembalikan    |
|      Prasyarat      |                 Petugas_telah_terautentikasi;_peminjaman_terpilih_berstatus_Dipinjam                 |
|Pascakondisi_berhasil|Pengembalian_tercatat_dengan_tanggal_kembali_dan_kondisi_peralatan;_status_peminjaman_menjadi_Selesai |
| Pascakondisi_gagal  |              Tidak_ada_pengembalian_baru_yang_tercatat;_status_peminjaman_tidak_berubah              |
|       Include       |                                 LAB-UC12:_Periksa_Kondisi_Peralatan                                  |
|    Collaboration    |                                LAB-CO02:_Catat_Pengembalian_Peralatan                                |


|               Sumber                |                  Hubungan                  |                Tujuan                |
|-------------------------------------|--------------------------------------------|--------------------------------------|
|              Peminjam               |                Association                 |LAB-UC01_Lihat_Ketersediaan_Peralatan |
|              Peminjam               |                Association                 |      LAB-UC03_Ajukan_Peminjaman      |
|              Mahasiswa              |Association_(khusus,_tetap_dari_Pertemuan_3)|    LAB-UC05_Cetak_Bukti_Pengajuan    |
|              Mahasiswa              |              Generalization_→              |               Peminjam               |
|                Dosen                |              Generalization_→              |               Peminjam               |
|        Petugas_Laboratorium         |                Association                 |    LAB-UC02_Kelola_Data_Peralatan    |
|        Petugas_Laboratorium         |                Association                 | LAB-UC06_Proses_Keputusan_Peminjaman |
|        Petugas_Laboratorium         |                Association                 |LAB-UC11_Catat_Pengembalian_Peralatan |
|         Kepala_Laboratorium         |                Association                 |  LAB-UC07_Lihat_Laporan_Peminjaman   |
|     LAB-UC03_Ajukan_Peminjaman      |     «include»_(tetap_dari_Pertemuan_3)     |    LAB-UC04_Periksa_Ketersediaan     |
|   LAB-UC05_Cetak_Bukti_Pengajuan    |     «extend»_(tetap_dari_Pertemuan_3)      |      LAB-UC03_Ajukan_Peminjaman      |
|   LAB-UC08_Tambah_Data_Peralatan    |              Generalization_→              |    LAB-UC02_Kelola_Data_Peralatan    |
|    LAB-UC09_Ubah_Data_Peralatan     |              Generalization_→              |    LAB-UC02_Kelola_Data_Peralatan    |
|    LAB-UC10_Hapus_Data_Peralatan    |              Generalization_→              |    LAB-UC02_Kelola_Data_Peralatan    |
|LAB-UC11_Catat_Pengembalian_Peralatan|                 «include»                  |  LAB-UC12_Periksa_Kondisi_Peralatan  |
|      LAB-CO01_(collaboration)       |               Realization_→                |      LAB-UC03_Ajukan_Peminjaman      |
|      LAB-CO02_(collaboration)       |               Realization_→                |LAB-UC11_Catat_Pengembalian_Peralatan |
