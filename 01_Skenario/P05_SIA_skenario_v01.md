• Pewarisan Civitas Akademika: Mahasiswa dan Dosen mewarisi Lihat
Kalender Akademik dari Civitas Akademika; asosiasi warisan tidak
digambar ulang dan skenario ditulis satu kali atas nama Civitas
Akademika.
• Nilai hanya dapat diinput oleh dosen pengampu mata kuliah tersebut.
• KHS hanya menampilkan nilai yang sudah dipublikasikan.
• Hapus Data Mahasiswa hanya untuk mahasiswa yang tidak memiliki
data akademik aktif.
• Diagram SIA Pertemuan 4 tidak diubah; produk tugas adalah
dokumen skenario, bukan diagram baru.


| Nama use case | SIA-UC07 Lihat Kalender Akademik |
| :--- | :--- |
| **Aktor** | Civitas Akademika (berlaku untuk Mahasiswa dan Dosen) |
| **Tujuan** | Civitas Akademika dapat melihat jadwal kegiatan akademik dalam satu semester |
| **Deskripsi** | Civitas Akademika membuka fungsi kalender akademik dan sistem menampilkan daftar jadwal kegiatan akademik |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Civitas Akademika membuka fungsi Lihat Kalender Akademik | |
| | 2. Sistem menampilkan kalender akademik semester aktif |
| **Skenario Alternative** | |
| 3. Data kalender akademik belum tersedia (cabang dari langkah 2) | 4. Sistem menampilkan pesan kalender akademik belum tersedia |
| **Skenario Akhir** | Use case selesai jika kalender akademik ditampilkan; jika data belum tersedia, use case selesai dengan pesan tersebut. |


| Nama use case | SIA-UC08 Input Nilai Mata Kuliah |
| :--- | :--- |
| **Aktor** | Dosen |
| **Tujuan** | Nilai mahasiswa pada mata kuliah yang diampu tersimpan ke dalam sistem |
| **Deskripsi** | Dosen pengampu memilih mata kuliah, mengisi nilai mahasiswa, dan menyimpan data nilai. Prasyarat: Dosen adalah pengampu mata kuliah tersebut |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Dosen memilih mata kuliah yang diampu | |
| | 2. Sistem menampilkan daftar mahasiswa pada mata kuliah tersebut |
| 3. Dosen mengisi nilai mahasiswa | |
| | 4. Sistem memeriksa validitas rentang nilai (harus berada dalam rentang sah) |
| 5. Dosen menyimpan data nilai | |
| | 6. Sistem menyimpan data nilai dan menampilkan konfirmasi penyimpanan |
| **Skenario Alternative** | |
| 7. Nilai yang diisi berada di luar rentang yang sah (cabang dari langkah 4) | 8. Sistem menolak isian nilai dan menampilkan pesan nilai di luar rentang yang sah |
| **Skenario Akhir** | Use case selesai jika data nilai tersimpan; jika nilai di luar rentang yang sah, data tidak tersimpan sampai nilai diperbaiki. |

| Nama use case | SIA-UC09 Lihat KHS |
| :--- | :--- |
| **Aktor** | Mahasiswa |
| **Tujuan** | Mahasiswa dapat melihat Kartu Hasil Studi (KHS) yang berisi nilai yang sudah dipublikasikan |
| **Deskripsi** | Mahasiswa memilih semester dan sistem menampilkan KHS dengan nilai yang telah dipublikasikan |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Mahasiswa membuka fungsi Lihat KHS dan memilih semester | |
| | 2. Sistem memeriksa ketersediaan nilai yang sudah dipublikasikan pada semester tersebut |
| | 3. Sistem menampilkan KHS berisi nilai yang sudah dipublikasikan |
| **Skenario Alternative** | |
| 4. Belum ada nilai yang dipublikasikan pada semester terpilih (cabang dari langkah 2) | 5. Sistem menampilkan pesan belum ada nilai yang dipublikasikan untuk semester ini |
| **Skenario Akhir** | Use case selesai jika KHS ditampilkan; jika belum ada nilai yang dipublikasikan, use case selesai dengan pesan tersebut. |

| Nama use case | SIA-UC10 Kelola Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terkelola melalui satu fungsi pengelolaan bersama |
| **Deskripsi** | Admin Akademik membuka fungsi pengelolaan data mahasiswa, memilih bentuk pengelolaan, dan menyimpan perubahan. Bentuk tambah, ubah, dan hapus dijabarkan pada tabel khususnya masing-masing |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Kelola Data Mahasiswa | |
| | 2. Sistem menampilkan daftar data mahasiswa |
| 3. Admin Akademik memilih bentuk pengelolaan, yaitu tambah, ubah, atau hapus | |
| | 4. Sistem menampilkan formulir sesuai bentuk pengelolaan yang dipilih |
| 5. Admin Akademik mengisi atau mengonfirmasi data mahasiswa | |
| | 6. Sistem memeriksa kelengkapan dan keabsahan data |
| 7. Admin Akademik menyimpan perubahan | |
| | 8. Sistem menyimpan perubahan dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 9. Data tidak lengkap atau tidak sah (cabang dari langkah 6) | 10. Sistem menolak penyimpanan dan menampilkan pesan kesalahan data |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak lengkap atau tidak sah, perubahan tidak tersimpan. |


| Nama use case | SIA-UC11 Tambah Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa baru tersimpan sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik mengisi data mahasiswa baru dan menyimpan data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik membuka fungsi Tambah Data Mahasiswa | |
| | 2. Sistem menampilkan formulir data mahasiswa baru |
| 3. Admin Akademik mengisi data mahasiswa baru | |
| | 4. Sistem memeriksa kelengkapan data |
| 5. Admin Akademik menyimpan data | |
| | 6. Sistem menyimpan data mahasiswa baru dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data tidak lengkap (cabang dari langkah 4) | 8. Sistem menolak penyimpanan dan meminta Admin Akademik melengkapi data |
| **Skenario Akhir** | Use case selesai jika data mahasiswa baru tersimpan; jika data tidak lengkap, data tidak tersimpan. |

| Nama use case | SIA-UC12 Ubah Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa berubah sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengubah datanya, dan menyimpan perubahan; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan diubah | |
| | 2. Sistem menampilkan data mahasiswa saat ini |
| 3. Admin Akademik mengubah data mahasiswa | |
| | 4. Sistem memeriksa perubahan data |
| 5. Admin Akademik menyimpan perubahan | |
| | 6. Sistem menyimpan data mahasiswa yang diubah dan menampilkan konfirmasi |
| **Skenario Alternative** | |
| 7. Data mahasiswa tidak ditemukan (cabang dari langkah 2) | 8. Sistem menampilkan pesan data mahasiswa tidak ditemukan |
| **Skenario Akhir** | Use case selesai jika perubahan data mahasiswa tersimpan; jika data tidak ditemukan, perubahan tidak tersimpan. |

| Nama use case | SIA-UC13 Hapus Data Mahasiswa |
| :--- | :--- |
| **Aktor** | Admin Akademik |
| **Tujuan** | Data mahasiswa terhapus sebagai bentuk khusus dari pengelolaan data mahasiswa |
| **Deskripsi** | Admin Akademik memilih data mahasiswa, mengonfirmasi penghapusan, dan sistem menghapus data tersebut; langkah bersama mengikuti Tabel skenario SIA-UC10 |
| **Kegiatan** | **Respon sistem** |
| **Skenario Normal** | |
| 1. Admin Akademik memilih data mahasiswa yang akan dihapus | |
| | 2. Sistem memeriksa status mahasiswa tidak memiliki data akademik aktif |
| 3. Admin Akademik mengonfirmasi penghapusan | |
| | 4. Sistem menghapus data mahasiswa dan menampilkan konfirmasi penghapusan |
| **Skenario Alternative** | |
| 5. Mahasiswa memiliki data akademik aktif (cabang dari langkah 2) | 6. Sistem menolak penghapusan dan menampilkan pesan mahasiswa masih memiliki data akademik aktif |
| **Skenario Akhir** | Use case selesai jika data mahasiswa terhapus; jika mahasiswa memiliki data akademik aktif, data tidak terhapus. |
