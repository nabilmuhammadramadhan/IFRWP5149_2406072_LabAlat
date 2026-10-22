|       Elemen        |                 LAB-UC03_-_Ajukan_peminjaman                  |
|---------------------|---------------------------------------------------------------|
|       Tujuan        |       Menghasilkan pengajuan peminjaman yang tersimpan        |
|     Aktor_utama     |                           Mahasiswa                           |
|  Sumber_kebutuhan   |                      LAB-R03 dan LAB-R04                      |
|       Pemicu        |         Mahasiswa memilih fungsi pengajuan peminjaman         |
|      Prasyarat      |    Mahasiswa telah terautentikasi; data peralatan tersedia    |
|Pascakondisi_berhasil|Pengajuan tersimpan dengan nomor dan status Menunggu keputusan |
| Pascakondisi_gagal  |       Tidak ada pengajuan baru yang berhasil tersimpan        |
|       Include       |                LAB-UC04 — Periksa ketersediaan                |
|   Extension_point   |           Bukti pengajuan tersedia, pada langkah 6            |
|       Extend        |            LAB-UC05 jika [mahasiswa memilih cetak]            |
<<<<<<< HEAD


|       Elemen        |                                                     SIA-UC04_-_Validasi_KRS                                                     |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------|
|       Tujuan        |                      Memeriksa kelengkapan, prasyarat mata kuliah, dan benturan jadwal dari pengajuan KRS                       |
|     Aktor_utama     |                                                       Sistem (Sub-fungsi)                                                       |
|  Sumber_kebutuhan   |                                                             SIA-R04                                                             |
|       Pemicu        |                            SIA-UC03 memanggil fungsi ini secara otomatis sebelum menyimpan pengajuan                            |
|      Prasyarat      |                 Mahasiswa telah memilih mata kuliah; data mata kuliah, prasyarat, dan jadwal tersedia di sistem                 |
|Pascakondisi_berhasil|                        Validasi terpenuhi (tidak ada pelanggaran aturan), sistem mengizinkan penyimpanan                        |
| Pascakondisi_gagal  |Validasi menemukan pelanggaran (prasyarat tak terpenuhi atau jadwal bentrok), mengembalikan pesan galat dan mencegah penyimpanan |
|       Include       |                                                                -                                                                |
|   Extension_point   |                                                                -                                                                |
|       Extend        |                                                                -                                                                |

|       Elemen        |                              SIA-UC05_-_Unduh_bukti_pengajuan                              |
|---------------------|--------------------------------------------------------------------------------------------|
|       Tujuan        |                  Menghasilkan salinan bukti pengajuan KRS bagi mahasiswa                   |
|     Aktor_utama     |                                         Mahasiswa                                          |
|  Sumber_kebutuhan   |                                          SIA-R05                                           |
|       Pemicu        |                Mahasiswa memilih opsi unduh bukti pada tampilan konfirmasi                 |
|      Prasyarat      |Pengajuan KRS telah berhasil tersimpan dan sistem sedang menampilkan konfirmasi penyimpanan |
|Pascakondisi_berhasil|               Dokumen bukti pengajuan berhasil diunduh ke perangkat pengguna               |
| Pascakondisi_gagal  |                  Bukti gagal diunduh atau dokumen tidak dapat dihasilkan                   |
|       Include       |                                             -                                              |
|   Extension_point   |                                             -                                              |
|       Extend        |                                    Memperluas SIA-UC03                                     |



|       Elemen        |                                    SIA-UC06_-_Proses_persetujuan_KRS                                    |
|---------------------|---------------------------------------------------------------------------------------------------------|
|       Tujuan        |         Menetapkan keputusan (setuju/tolak) terhadap pengajuan KRS dan menyimpan catatan dosen          |
|     Aktor_utama     |                                               Dosen wali                                                |
|  Sumber_kebutuhan   |                                                 SIA-R06                                                 |
|       Pemicu        |                       Dosen wali memilih pengajuan KRS mahasiswa untuk dievaluasi                       |
|      Prasyarat      |Dosen wali telah terautentikasi; terdapat pengajuan KRS yang berstatus "menunggu persetujuan dosen wali" |
|Pascakondisi_berhasil|   Pengajuan KRS diperbarui menjadi berstatus disetujui atau ditolak, dan catatan keputusan tersimpan    |
| Pascakondisi_gagal  |           Tidak ada perubahan status atau catatan yang berhasil tersimpan pada pengajuan KRS            |
|       Include       |                                                    -                                                    |
|   Extension_point   |                                                    -                                                    |
|       Extend        |                                                    -                                                    |
=======
>>>>>>> 22994a0012dd8e054e6523f15a1fc203a0cd23c3
