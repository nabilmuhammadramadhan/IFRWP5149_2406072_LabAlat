<!-- skenario -->
Skenario tugas berikut fiktif untuk praktikum dan berbeda dari tugas
Pertemuan 2 (jadwal kuliah) dan Pertemuan 3 (pengajuan KRS).
Mahasiswa dan dosen sama-sama merupakan Civitas Akademika yang
dapat melihat kalender akademik. Dosen menginput nilai mata kuliah yang
diampunya setelah masa perkuliahan berakhir. Mahasiswa melihat Kartu
Hasil Studi (KHS) untuk semester yang nilainya sudah dipublikasikan. Admin
Akademik mengelola data mahasiswa: menambah data mahasiswa baru,
mengubah data mahasiswa, dan menghapus data mahasiswa. Dua use case
utama, Input Nilai Mata Kuliah dan Lihat KHS, ditunjukkan realisasinya oleh
collaboration yang bersesuaian.

<!-- Batas dan asumsi -->
• Kode kebutuhan dimulai dari SIA-R07 agar SIA-R01 dan SIA-R02
(Pertemuan 2) serta SIA-R03 sampai SIA-R06 (Pertemuan 3) tetap
mempunyai identitas berbeda.
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran.
• Kalender akademik pada tugas ini adalah agenda resmi institusi (awal
semester, batas KRS, masa ujian, dan sejenisnya); jangan
menyamakannya dengan jadwal kuliah pada Pertemuan 2.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut. Nilai
yang diinput belum terpublikasi sebelum dinyatakan resmi oleh ketentuan
tugas ini: KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki data
akademik aktif. Ketentuan ini fiktif untuk latihan.
• Pengajuan KRS tetap digambar sebagai bagian diagram kumulatif dari
Pertemuan 3. Pembayaran dan perancangan basis data berada di luar
tugas ini.

<!-- aktor -->
|      Aktor      |          Kedudukan          |                                                             Tujuan_terhadap_sistem                                                              |
|-----------------|-----------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
|Civitas_Akademika|       Umum_(general)        |                               Peran_umum_bagi_pengguna_akademik._Mewariskan_fungsinya_kepada_Mahasiswa_dan_Dosen.                               |
|    Mahasiswa    |Khusus_dari_Civitas_Akademika|Melihat_kalender_akademik_(diwarisi),_ditambah_melihat_jadwal_kuliah,_mengajukan_KRS,_mengunduh_bukti,_dan_melihat_KHS_sebagai_fungsi_khususnya. |
|      Dosen      |Khusus_dari_Civitas_Akademika|                      Melihat_kalender_akademik_(diwarisi),_ditambah_menginput_nilai_mata_kuliah_sebagai_fungsi_khususnya.                       |
| Admin_Akademik  |   Tetap_dari_Pertemuan_2    |                                              Mengelola_jadwal_kuliah_dan_mengelola_data_mahasiswa.                                              |
|   Dosen_Wali    |   Tetap_dari_Pertemuan_3    |                                                            Memproses_keputusan_KRS.                                                             |
 
<!-- Katalog Use Case Gabungan -->
|   ID   |      Nama_use_case      |                           Peran_dalam_model                           |Sumber_kebutuhan |
|--------|-------------------------|-----------------------------------------------------------------------|-----------------|
|SIA-UC01|   Lihat_Jadwal_Kuliah   |            Tetap_dari_Pertemuan_2;_fungsi_khusus_Mahasiswa            |     SIA-R01     |
|SIA-UC02|  Kelola_Jadwal_Kuliah   |          Tetap_dari_Pertemuan_2;_fungsi_utama_Admin_Akademik          |     SIA-R02     |
|SIA-UC03|       Ajukan_KRS        |            Tetap_dari_Pertemuan_3;_fungsi_khusus_Mahasiswa            |     SIA-R03     |
|SIA-UC04|      Validasi_KRS       |       Tetap_dari_Pertemuan_3;_perilaku_yang_disertakan_SIA-UC03       |     SIA-R04     |
|SIA-UC05|Unduh_Bukti_Pengajuan_KRS|       Tetap_dari_Pertemuan_3;_tambahan_bersyarat_pada_SIA-UC03        |     SIA-R05     |
|SIA-UC06|  Proses_Keputusan_KRS   |            Tetap_dari_Pertemuan_3;_fungsi_utama_Dosen_Wali            |     SIA-R06     |
|SIA-UC07| Lihat_Kalender_Akademik |      Baru_pada_Pertemuan_4;_fungsi_aktor_umum_Civitas_Akademika       |     SIA-R07     |
|SIA-UC08| Input_Nilai_Mata_Kuliah |  Baru_pada_Pertemuan_4;_fungsi_khusus_Dosen;_direalisasikan_SIA-CO01  |SIA-R08,_SIA-R12 |
|SIA-UC09|        Lihat_KHS        |Baru_pada_Pertemuan_4;_fungsi_khusus_Mahasiswa;_direalisasikan_SIA-CO02|SIA-R09,_SIA-R12 |
|SIA-UC10|  Kelola_Data_Mahasiswa  |Baru_pada_Pertemuan_4;_use_case_UMUM_bagi_SIA-UC11,_SIA-UC12,_SIA-UC13 |     SIA-R10     |
|SIA-UC11|  Tambah_Data_Mahasiswa  |         Baru_pada_Pertemuan_4;_use_case_KHUSUS_dari_SIA-UC10          |     SIA-R11     |
|SIA-UC12|   Ubah_Data_Mahasiswa   |         Baru_pada_Pertemuan_4;_use_case_KHUSUS_dari_SIA-UC10          |     SIA-R11     |
|SIA-UC13|  Hapus_Data_Mahasiswa   |         Baru_pada_Pertemuan_4;_use_case_KHUSUS_dari_SIA-UC10          |     SIA-R11     |

<!-- generalization aktor  -->
Mahasiswa adalah bentuk khusus dari Civitas Akademika, dan Dosen adalah bentuk khusus dari Civitas Akademika. Alasan: Keduanya berbagi fungsi yang sama, yaitu melihat kalender akademik (SIA-UC07).
Asosiasi ke SIA-UC07 digambar satu kali, yaitu dari Civitas Akademika.
Asosiasi Mahasiswa dan Dosen ke fungsi spesifik mereka (seperti KRS atau Input Nilai) digambar langsung dari masing-masing aktor khusus.

<!-- generalization use case -->
Keputusan Generalization Use Case: SIA-UC11, SIA-UC12, dan SIA-UC13 adalah bentuk khusus dari SIA-UC10 Kelola Data Mahasiswa.
Tambah Data Mahasiswa: Menghasilkan pencatatan data mahasiswa baru di dalam sistem.
Ubah Data Mahasiswa: Menghasilkan data mahasiswa yang informasinya telah diperbarui/berubah.
Hapus Data Mahasiswa: Menghasilkan data mahasiswa yang terhapus dari sistem, dengan syarat mahasiswa tersebut tidak memiliki data akademik aktif.

<!-- collaboration -->
|   ID   |  Nama_collaboration   |   Use_case_yang_direalisasikan   |
|--------|-----------------------|----------------------------------|
|SIA-CO01|Input_Nilai_Mata_Kuliah|SIA-UC08:_Input_Nilai_Mata_Kuliah |
|SIA-CO02|       Lihat_KHS       |       SIA-UC09:_Lihat_KHS        |

<!-- use case description baru -->
|       Elemen        |                              SIA-UC08:_Input_Nilai_Mata_Kuliah                               |
|---------------------|----------------------------------------------------------------------------------------------|
|     ID_dan_nama     |                              SIA-UC08:_Input_Nilai_Mata_Kuliah                               |
|  Sumber_kebutuhan   |                                     SIA-R08_dan_SIA-R12                                      |
|       Tujuan        |               Nilai_mahasiswa_untuk_suatu_mata_kuliah_tercatat_di_dalam_sistem               |
|     Aktor_utama     |                                            Dosen                                             |
|       Pemicu        |Dosen_memilih_menu_input_nilai_dan_memilih_mata_kuliah_yang_telah_selesai_masa_perkuliahannya |
|      Prasyarat      |      Dosen_telah_terautentikasi_dan_merupakan_dosen_pengampu_dari_mata_kuliah_tersebut       |
|Pascakondisi_berhasil|                     Nilai_mata_kuliah_berhasil_disimpan_ke_dalam_sistem                      |
| Pascakondisi_gagal  |                Tidak_ada_nilai_baru_yang_tersimpan_(sistem_menolak_perubahan)                |
|       Include       |                                              -                                               |
|       Extend        |                                              -                                               |
|    Collaboration    |                              SIA-CO01:_Input_Nilai_Mata_Kuliah                               |








