<!-- use case description baru -->
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
