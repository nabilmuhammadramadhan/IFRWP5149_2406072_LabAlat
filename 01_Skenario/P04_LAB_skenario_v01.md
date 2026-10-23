Skenario ini merupakan bahan latihan jobsheet yang melanjutkan potongan model Pertemuan 3, bukan hasil pengumpulan kebutuhan laboratorium nyata. Dalam skenario ini, peminjaman peralatan laboratorium untuk kegiatan praktikum dan penelitian dapat dilakukan oleh mahasiswa maupun dosen, di mana keduanya memiliki akses untuk melihat ketersediaan alat dan mengajukan peminjaman. Di sisi lain, petugas laboratorium bertanggung jawab mengelola data peralatan—seperti menambah, mengubah, dan menghapus alat yang sudah tidak digunakan—serta mencatat pengembalian beserta pemeriksaan kondisi alat setelah peminjaman disetujui dan selesai digunakan.

Dua use case utama dalam model ini, yaitu Ajukan Peminjaman dan Catat Pengembalian Peralatan, ditunjukkan realisasinya melalui collaboration yang bersesuaian. Sementara itu, seluruh fungsi pada Pertemuan 3 tetap berlaku dan harus digambar, meliputi pemeriksaan ketersediaan dalam pengajuan, pencetakan bukti pengajuan oleh mahasiswa, proses keputusan peminjaman oleh petugas, serta penyusunan laporan peminjaman untuk kepala laboratorium. Dengan demikian, diagram Pertemuan 4 ini bersifat akumulatif yang menambahkan elemen baru ke diagram sebelumnya, bukan sebagai diagram baru yang menggantikannya.

<!-- Batas sistem dan aturan -->
• Sistem mencatat dan menyediakan informasi; perpindahan fisik alat tidak
terjadi di dalam perangkat lunak (tetap dari Pertemuan 3).
• Pengguna telah terautentikasi dan memiliki hak akses sesuai peran (tetap
dari Pertemuan 3).
• Pengembalian hanya dapat dicatat untuk peminjaman berstatus Dipinjam.
Peminjaman yang masih Menunggu Keputusan atau Ditolak tidak dapat
dicatat pengembaliannya.
• Kondisi peralatan pada pengembalian dicatat dengan salah satu nilai: Baik,
Rusak Ringan, atau Rusak Berat.
• Hapus Data Peralatan hanya untuk peralatan yang tidak sedang dipinjam
dan tidak memiliki pengajuan aktif.
• Keterlambatan dan denda belum dimodelkan pada pertemuan ini. Tuliskan
sebagai pertanyaan terbuka pada berkas kebutuhan, jangan mengarang
aturan denda.
• Kriteria penerimaan model: semua kebutuhan LAB-R01 sampai LAB-R11
mempunyai representasi pada diagram kumulatif, arah generalization dan
realization benar, dan diagram konsisten dengan deskripsinya.

<!-- aktor umum dan aktor khusus -->
|       Aktor        |                 Kedudukan                  |                                                            Tujuan_terhadap_sistem                                                             |
|--------------------|--------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
|      Peminjam      |   Umum_(general),_baru_pada_Pertemuan_4    |                             Peran_umum_bagi_peminjam_peralatan._Mewariskan_fungsinya_kepada_Mahasiswa_dan_Dosen.                              |
|     Mahasiswa      |Khusus_dari_Peminjam,_tetap_dari_Pertemuan_3|Melihat_ketersediaan_dan_mengajukan_peminjaman_(diwarisi_dari_Peminjam),_ditambah_mencetak_bukti_pengajuan_sebagai_asosiasi_khususnya_sendiri. |
|       Dosen        |Khusus_dari_Peminjam,_baru_pada_Pertemuan_4 |                                   Melihat_ketersediaan_dan_mengajukan_peminjaman_(diwarisi_dari_Peminjam).                                    |
|Petugas_Laboratorium|           Tetap_dari_Pertemuan_3           |                        Mengelola_data_peralatan,_memproses_keputusan_peminjaman,_dan_mencatat_pengembalian_peralatan.                         |
|Kepala_Laboratorium |           Tetap_dari_Pertemuan_3           |                                                          Melihat_laporan_peminjaman.                                                          |

<!-- katalog use case -->
|   ID   |       Nama_use_case        |                                        Peran_dalam_model                                        |Sumber_kebutuhan |
|--------|----------------------------|-------------------------------------------------------------------------------------------------|-----------------|
|LAB-UC01|Lihat_Ketersediaan_Peralatan|                       Tetap_dari_Pertemuan_3;_fungsi_aktor_umum_Peminjam                        |LAB-R01,_LAB-R07 |
|LAB-UC02|   Kelola_Data_Peralatan    |             Tetap_dari_Pertemuan_3;_use_case_UMUM_bagi_LAB-UC08,_LAB-UC09,_LAB-UC10             |LAB-R02,_LAB-R08 |
|LAB-UC03|     Ajukan_Peminjaman      |Tetap_dari_Pertemuan_3;_fungsi_aktor_umum_Peminjam;_menyertakan_LAB-UC04;_direalisasikan_LAB-CO01|LAB-R03,_LAB-R07 |
|LAB-UC04|    Periksa_Ketersediaan    |                    Tetap_dari_Pertemuan_3;_perilaku_yang_disertakan_LAB-UC03                    |     LAB-R03     |
|LAB-UC05|   Cetak_Bukti_Pengajuan    |             Tetap_dari_Pertemuan_3;tambahan_bersyarat_pada_LAB-UC03_melalui«extend»             |     LAB-R04     |
|LAB-UC06|Proses_Keputusan_Peminjaman |                          Tetap_dari_Pertemuan_3;_fungsi_utama_petugas                           |     LAB-R05     |
|LAB-UC07|  Lihat_Laporan_Peminjaman  |                    Tetap_dari_Pertemuan_3;_fungsi_utama_kepala_laboratorium                     |     LAB-R06     |
|LAB-UC08|   Tambah_Data_Peralatan    |                      Baru_pada_Pertemuan_4;_use_case_KHUSUS_dari_LAB-UC02                       |     LAB-R08     |
|LAB-UC09|    Ubah_Data_Peralatan     |                      Baru_pada_Pertemuan_4;_use_case_KHUSUS_dari_LAB-UC02                       |     LAB-R08     |
|LAB-UC10|    Hapus_Data_Peralatan    |                      Baru_pada_Pertemuan_4;_use_case_KHUSUS_dari_LAB-UC02                       |     LAB-R08     |
|LAB-UC11|Catat_Pengembalian_Peralatan|              Baru_pada_Pertemuan_4;_fungsi_utama_petugas;_direalisasikan_LAB-CO02               |     LAB-R09     |
|LAB-UC12| Periksa_Kondisi_Peralatan  |                    Baru_pada_Pertemuan_4;_perilaku_yang_disertakan_LAB-UC11                     |     LAB-R10     |

<!-- generalization aktor -->
Tuliskan dua keputusan pemodelan berikut pada berkas skenario, lengkap
dengan alasannya:
• Mahasiswa adalah bentuk khusus dari Peminjam, dan Dosen adalah
bentuk khusus dari Peminjam. Alasan: keduanya berbagi fungsi yang
sama, yaitu melihat ketersediaan peralatan dan mengajukan peminjaman.
• Asosiasi ke LAB-UC01 dan LAB-UC03 digambar satu kali, yaitu dari
Peminjam. Jangan menggambar garis yang sama dari Mahasiswa dan dari
Dosen.
• Asosiasi Mahasiswa ke LAB-UC05 Cetak Bukti Pengajuan tidak ikut
dipindahkan dan tidak dihapus, karena fungsi itu khusus mahasiswa.
Asosiasi ini menjadi contoh asosiasi tambahan milik aktor khusus.
• Periksa arah panah pada gambar: ujung segitiga kosong harus menempel
pada Peminjam, bukan pada Mahasiswa dan bukan pada Dosen. Karena
Peminjam digambar di tengah, panah Mahasiswa mengarah ke bawah dan
panah Dosen mengarah ke atas; keduanya berakhir pada Peminjam.


<!--  Perbandingan diagram Pertemuan 3 dan diagram Pertemuan 4 -->
|             Kelompok              |                                                                                                                                                                                                    Isi                                                                                                                                                                                                     |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Tetap_sama_dari_Pertemuan_3    |Aktor_Mahasiswa,_Petugas_Laboratorium,_dan_Kepala_Laboratorium;_use_case_LAB-UC01_sampai_LAB-UC07;relasi«include»_LAB-UC03_ke_LAB-UC04;relasi«extend»LAB-UC05_ke_LAB-UC03_lengkap_dengan_condition[mahasiswa_memilih_cetak]_dan_extension_point_Bukti_pengajuan_tersedia;_asosiasi_Petugas_Laboratorium_ke_LAB-UC02_dan_LAB-UC06;_asosiasi_Kepala_Laboratorium_ke_LAB-UC07;_asosiasi_Mahasiswa_ke_LAB-UC05. |
|Berubah_karena_generalization_aktor|                                          Asosiasi_ke_LAB-UC01_dan_LAB-UC03_yang_pada_Pertemuan_3_digambar_dari_Mahasiswa_kini_digambar_satu_kali_dari_Peminjam._Fungsi_mahasiswa_tidak_hilang:_mahasiswa_mewarisinya_dari_Peminjam._Inilah_satu-satunya_perubahan_garis_pada_diagram_lama,_dan_alasannya_adalah_aturan_generalization,_bukan_penghapusan_fungsi.                                           |
|     Ditambah_pada_Pertemuan_4     |                                  Aktor_Peminjam_dan_Dosen;_dua_generalization_aktor;_use_case_LAB-UC08,_LAB-UC09,_LAB-UC10_beserta_tiga_generalization_use_case_ke_LAB-UC02;use_case_LAB-UC11_dan_LAB-UC12_beserta_relasi«include»_di_antara_keduanya_dan_asosiasi_Petugas_Laboratorium_ke_LAB-UC11;_collaboration_LAB-CO01_dan_LAB-CO02_beserta_dua_relasi_realization.                                   |
 

