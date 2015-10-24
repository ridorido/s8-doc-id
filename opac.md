# Bab 10

1 Opac (Online Public Access Catalog)

The library is not only a diary of the human race, but marks an act of faith in the continuity of humanity. --Vartan Gregorian 

OPAC ( Online Public Access Catalog ), merupakan sarana penelusuran yang diperuntukkan bagi user. OPAC dalam Senayan ini terdiri dari Simple Search (pencarian sederhana), Advanced Search (pencarian canggih), navigasi Library Information (informasi tentang perpustakaan), navigasi Help on Search dan Librarian Login. Pada Simple Search, pencarian dapat dilakukan dengan mengetikkan kata kunci (judul, pengarang, subyek...) pada kolom yang tersedia. Sedangkan pada Advanced Search terdapat tiga kolom pencarian yaitu: khusus Title, khusus Author, ISBN/ISSN dan khusus Subject. Untuk memperoleh ketepatan pencarian disediakan pula pilihan Location, Collection Type dan GMD. Informasi pada Library Information dapat disesuaikan dengan perpustakaan/institusi terkait dengan mengedit file libnfo.inc.php yang terletak pada folder lib. Sementara untuk mengubah Help on Search, dilakukan dengan mengedit file help.inc.php yang terletak pada folder lib. Tampilan awal hasil pencarian bibliografi di dalam OPAC memuat gambar/image, judul, Pengarang. Selain itu ditambah dengan tombol Detail (untuk melihat detail data bibliografi) dan XML (untuk mendapatkan format XML). Tampilan Detail, memuat informasi Title (judul), Edition, Call Number, ISSN/ISBN, Author (pengarang), Topics, Classification, Series, Title, GMD, Language (bahasa), Publisher (penerbit), Publish Year (tahun terbit), Publish Place (tempat terbit), Collation, Abstrac/Notes, Location, Image (gambar) dan File Attachment yang dapat diunduh, Availability (ketersediaan: berisi informasi total item, item tersedia dan item terpinjam), Topics dan Author memiliki fasilitas keterkaitan antar dokumen. Jadi ketika kita klik Topics atau author dalam Detail OPAC maka akan muncul dokumen dengan topik atau pengarang yang sama.

Dalam OPAC ini pula, di berikan fasilitas untuk mengubah bahasa pengantar. OPAC Senayan telah mempunyai 5 bahasa pengantar; yaitu Arab, Indonesia, Inggris, Jerman dan Spanyol.







1.1 Custom Field Record List

Pada Aplikasi Senayan stable 8 ini, ditambahi dengan fasilitas penampilan field record secara cuztomise. Penambahan ini dapat dilakukan dengan mengedit file custom_frontpage_record.inc.php yang terdapat pada folder template OPAC. Jadi jika anda ingin mengubah tampilan yang disediakan, dan anda menggunakan template default, anda harus mengedit file custom_frontpage_record.inc.php yang ada di template/default/. Isi dari file ini adalah:

// change "0" value to "1" to enable field

// $custom_fields['edition'] = array(1, lang_mod_biblio_field_edition);

$custom_fields['edition'] = array(0, lang_mod_biblio_field_edition); --> untuk menampilkan edisi

$custom_fields['isbn_issn'] = array(0, lang_mod_biblio_field_isbn); --> untuk menampilkan ISBN

$custom_fields['collation'] = array(0, lang_mod_biblio_field_collation); --> untuk menampilkan Colasi

$custom_fields['series_title'] = array(0, lang_mod_biblio_field_series); --> untuk menampilkan Seri

$custom_fields['call_number'] = array(1, lang_mod_biblio_field_call_number); --> untuk menampilkan call number

Caranya adalah dengan mengubah angka 0 menjadi angka 1

1.2 Tampilan Multimedia

File multimedia yang diupload pada modul Bibliografi akan ditampilkan pada modul OPAC senayan, berikut adalah contoh tampilan file .flv



1.3 Tampilan PDF Streaming

Mulai Stable13, Senayan telah mendukung tampilan dokumen lampiran dalam bentuk streaming. Untuk menampilkan dibutuhkan Flash Player pada browser yang digunakan. 



1.4 Boolean Logic di OPAC 

Mulai Senayan3-stable10, sistem pencarian di OPAC sudah mendukung logika boolean. Pada proses pencarian dapat digunakan operator OR, NOT dan AND. 

Misalnya: subject=politik NOT politic, hasilnya adalah politik tanpa memunculkan politic. title=mapping AND author=dwikorita, hasilnya adalah koleksi yang berjudul mapping dan pengarangnya dwikorita.



1.5 Member Area

Mulai Senayan3-Stable12, senayan mempunyai fitur Member Area. Perubahan besar di Member Area terjadi di Stable 15/Matoa. Pada fitur ini anggota dapat melakukan login dengan menggunakan ID anggota dan password yang sebelumnya sudah ditentukan oleh pustakawan sewaktu input data anggota. Pada Stable12 ketika anggota login, anggota dapat melihat koleksi yang dipinjam, serta melakukan penggantian password. Namun pada Stable15/Matoa fasilitas ini diperluas dengan fasilitas mengunduh daftar pinjaman, mengunduh daftar riwayat peminjaman, serta pemesanan via Email.









Selain daftar riwayat peminjaman dan fasiltitas unduh, ada fitur Kerangjang Judul. Keranjang ini dapat diisi judul-judul yang menurut member menarik dan akan di pesan.

Cara pengisiannya adalah, dengan menuju ke halaman OPAC, muncul tampilan berikut:



Tampilan di atas, muncul jika anda melakukan login sebagai member. Untuk mengisi silakan contreng kotak di tiap akhir judul, lalu klik “Taruh Pilihan yang anda tandai ke keranjang”. Hasilnya adalah sebagai berikut.



Untuk mengirim pesanan ke Pustakawan, silakan klik “Reservasi ditambahkan ke dalam Keranjang”. Maka jika berhasil akan muncul tampilan sebagai berikutuntuk melakukan pengiriman pesanan via email, silakan lihat seting email di Tips dan Trik pada bagian Mensetting Email server. :



Pada email pustakawan akan muncul kiriman email sebagai berikut:

