# Bab 13

1 Tips dan Trik

Knowledge is free at the library. Just bring your own container. - Unknown

1.1 Pengaturan Ukuran barcode, label, kartu anggota dan nota peminjaman

Setting ukuran barcode dan label dapat dilakukan dengan melakukan editing file printed_settings.inc.php yang terletak di /senayan3-stable7/admin/admin_template/.

Dalam file ini akan didapatkan baris-baris kode sebagai berikut: 

// label print settings

/* measurement in cm */

$page_width = 50;

$page_height = 30;

$page_margin = 0.2;

$items_per_row = 3;

$items_margin = 0.05;

$box_width = 8;

$box_height = 3.3;

$include_header_text = 1; // change to 0 if dont want to use header in each label

$header_text = ''; // keep empty if you want to use Library Name as a header text

// item barcode print settings

/* measurement in cm */

$barcode_page_width = 50;

$barcode_page_height = 30;

$barcode_page_margin = 0.2;

$barcode_items_per_row = 3;

$barcode_items_margin = 0.1;

$barcode_box_width = 7;

$barcode_box_height = 5;

$barcode_include_header_text = 1; // change to 0 if dont want to use header in each barcode

$barcode_cut_title = 50; // maximum characters in title to appear in each barcode. change to 0 if you dont want the title cutted

$barcode_header_text = ''; // keep empty if you want to use Library Name as a header text

// member card print settings

/* measurement in cm */

$card_page_width = 50;

$card_page_height = 50;

$card_page_margin = 0.2;

$card_items_per_row = 2;

$card_items_margin = 0.1;

$card_box_width = 11;

$card_box_height = 6;

$card_header_text = $sysconf['library_name'];

$card_photo_width = 3;

$card_photo_height = 3;

// barcode generator print settings

$barcodegen_page_width = 29.7;

$barcodegen_page_height = 21;

$barcodegen_page_margin = 0.2;

$barcodegen_items_margin = 0.05;

$barcodegen_include_border = 0;

/* Receipt Printing */ 

$receipt_width = '15cm'; 

$receipt_font = 'serif'; 

$receipt_color = '#000'; 

$receipt_margin = '5px'; 

$receipt_padding = '5px'; 

$receipt_border = '1px dashed #000'; 

$receipt_fontSize = '7pt'; 

$receipt_header_fontSize = '8pt'; 

$receipt_titleLength = 100;

?>

Jika anda menginginkan setingan untuk barcode, label dan kartu anggota  berbeda pada tiap template, maka anda dapat mengcopi file print_settings.inc.php ke dalam tiap template admin, dan mengubahnya sesuai selera anda.

1.2 Pencarian di OPAC dengan kata kunci minimal 3 huruf? 

1. Buka file my.ini yang terletak di /mysql/my.ini Pada baris 43 tuliskan script berikut: 

ft_min_word_len=3 

1. Kemudian simpan dan restart server mysql. 

2. Bukalah database Senayan dengan phpmyadmin 

3. Klik tabel biblio, kemudian lihat bagian Indexes pada bagian bawah. Anda akan menemukan keyname title_ft dengan field title. Hapus baris tersebut dengan klik X.



1. Kemudian pada “Create an Index on” isikan 1 dan klik Go, akan muncul tampilan sebagai berikut:



1. Isilah kolom kosong diatas sehingga menjadi seperti berikut



Yang perlu anda ubah adalah: index name, index type dan Field Klik SAVE. Restart Mysql anda, dan OPAC Senayan sudah dapat mencari dengan kata kunci 3 karakter. 



1.3 Tutorial Upgrade Aplikasi Perpustakaan Senayan

Pada kali ini, tim Senayan Developer Community akan memberikan tips dan trik bagaimana melakukan upgrade penggunaan Senayan dari versi lama hingga versi terkahir. perlu diketahui pada tanggal 13 Maret 2008, Senayan dirilis ke publik dan diberi nama pengembangannya Senayan3-Stable1. Hingga saat ini Senayan yang telah dirilis hingga Stable10. Banyak sekali perbaikan perbaikan bugs serta penambahan fitur dan modul di saat pertama kali rilis hingga saat ini. lalu muncul pertanyaan bagaimana jika kita telah menggunakan Senayan versi lama, dan ingin meng-upgrade ke versi terbaru? berikut ini kami berikan tips dan trik untuk melakukan upgrade Senayan versi lama ke versi yang terbaru.

Pertama, perlu diketahui upgrade Senayan harus dilakukan secara bertahap dan berurut. Contohnya jika kita telah menggunakan Senayan3-Stable1, maka untuk melakukan upgrade ke Senayan3 Stable9 harus dilakukan secara berurut sesuai dengan versi setingkat di atasnya. artinya lakukan upgrade dari Stable1 ke Stable2 terlebih dahulu, kemudian lanjut ke Stable3 dan seterusnya hingga ke Stable9.

Kedua, berikut ini cara-cara melakukan upgrade secara teknis.

- Upgrade menggunakan phpmyadmin

1. buka browser, ketikkan alamat http://localhost/phpmyadmin



2. masukan user name dan password anda.

3. pilih database senayan dengan cara mengklik nama databasenya.



4. klik tab Import.



5. klik browse.



6. cari file upgrade_stable3.sql (jika anda menggunakan Senayan3-Stable2) dan cari file upgrade_stable4.sql (jika anda menggunakan Senayan3-Stable4), (harus bertingkat). file tersebut berada di path ../upgrade/old_sql/..



7. lalu klik Go.

8. ulangi langkah no 6 dan 7 sampai ke upgrade_stable10_patch1.sql.

9. lalu lakukan editing ulang pada file sysconfig.inc.php yang ada di Senayan3-Stable9. sesuaikan konfigurasinya dengan sysconfig.inc.php yang ada pada Senayan versi lama yang anda gunakan. Sesuaikan pula letak file mysqldump anda (letakknya juga di file sysconfig.inc.php).



10. Copy dan paste images dan files yang ada pada Senayan versi lama (yang anda gunakan saat ini) ke Senayan versi terbaru.



11. buka browser baru, dan masukkan alamat untuk untuk mengakses Senayan versi terbaru anda.



12. selamat mencoba.



1.4 Mengubah dan menambahkan informasi pada Library Information di OPAC 

Tips ini, mulai Senayan3-stable9 dipindah pada menu System --> Content 

1.5 Mengubah dan menambahkan informasi pada Help on Search

Tips ini, mulai Senayan3-stable9 dipindah pada menu System --> Content 

1.6 Mengubah/Membuat bahasa Pengantar baru

• Sejak Senayan3-stable11, penambahan bahasa pengantar mulai menggunakan fungsi gettext dalam PHP untuk mengganti nilai constant dalam file bahasa sebelumnya (misalnya indonesia.lang.inc.php atau english.lang.inc.php). Kini Default Application Language, Senayan telah menyediakan tiga (3) bahasa yaitu bahasa Indonesia, bahasa Inggris dan bahasa Jerman. untuk bahasa Inggris.

• Petunjuk berikut ini hanya memberikan pengantar kilat untuk menambahkan terjemahan bahasa di Senayan. Untuk lebih lengkapnya penjelasan tentang membuat aplikasi banyak bahasa bisa ditemukan dihttp://carsonified.com/blog/features/webapps/give-your-web-app-international-appeal/ dan dihttp://carsonified.com/blog/dev/give-your-web-app-international- appeal-part-ii/

1. Langkah pertama adalah mengunduh program PoEDIT 

• Unduh PoEdit dari http://www.poedit.net/ dan menginstalnya. Aplikasi ini tersedia dalam versi Window / Linux / Mac.

2. Membuat Folder / Direktori baru “Bahasa”

(a) Buka direktori senayan3 \ lib \ lang \ locale

(b) Buat folder menggambarkan “bahasa” dan negara terjemahan tersebut. Misalnya singkatan en_US: untuk Inggris / Amerika Serikat. Meskipun tidak sangat diperlukan untuk menggunakan konvensi ini, akan lebih baik jika bisa mengikuti secara konsisten. Daftar kode-kode bahasa dapat dilihat di http://www.gnu.org/software/gettext/manual/gettext.html#Usual-Language-Codes dan kode singkatan untuk negara di http://www.gnu.org/software/gettext/manual/gettext.html#Country-Codes

(c) Masuk ke dalam folder baru tadi dan membuat folder lain yang disebut: LC_MESSAGES

(d) Misalkan yang dibuat adalah id_ID, maka sekarang di direktori tadi terdapat sesuatu seperti id_ID / LC_MESSAGES

3. Membuat KATALOG untuk menciptakan terjemahan

(a) Mulai PoEdit

(b) Klik Menu "File"> "New Catalog"

• Tab "Project info":

• "Project Name and Version": (Opsional) Masukkan Senayan3

• "Team": (Opsional) Masukkan nama Anda

• "Team's email address": (Opsional) Masukkan email Anda

• "Language": Pilih bahasa yang anda ingin menerjemahkan ke

• "Country": Pilih negara untuk bahasa

• "Charset": Gunakan utf-8

• "Source code charset": Gunakan utf-8

• "Plural forms": Ini sedikit lebih rumit. Jika bahasa Anda hanya memiliki satu bentuk jamak bentuk menggunakan: nplurals = 2; plural = n! = 1; Untuk bahasa lain Anda dapat menemukan daftar kemungkinan bentuk jamak di http://translate.sourceforge.net/wiki/l10n/pluralforms

• "Base Path": Masukkan: ../../../../../

• "Paths" (Klik tombol "New Item"): Masukkan: . (hanya titik) 

• Tab "Kata kunci"

• Tambahkan dua baris: __ (Dua garis bawah)_ngettext

(c) Tekan ok dan menyimpan file di bawah senayan3 \ lib \ lang \ locale \ (YOUR LANGUAGE) \ LC_MESSAGES dengan nama 

messages.po

4. Memulai transalasi

(a) Pertama-tama Anda harus mengambil semua string yang akan diterjemahkan. Pergi ke "Catalog"> "Update from sources" (atau cukup klik tombol ketiga dari kiri di jendela utama)

(b) Sekarang mulai menerjemahkan setiap baris dengan mengkliknya dan memasuki terjemahan di bagian bawah jendela

(c) Setelah selesai pergi ke "File"> "Save" (atau tekan tombol kedua dari kiri)

5. Menyajikan hasil terjemahan 

(a) Buka file \ senayan3 \ lib \ lang \ localisation.php dan pada baris seperti ini di akhir harus diubah/ditambahkan: 

$available_languages [] = array ( 'xx_XX', _ ( 'NAMA BAHASA INGGRIS'), 'NAMA NATIVE Bahasa'); 

CATATAN

• Ketika mengklik kanan pada sebuah baris, Anda dapat melihat di mana konteks (kode sumber) string digunakan. 

• Jika pada suatu saat ingin dilakukan mengubah terjemahan yang sama berulang kali, anda harus melakukannya satu persatu karena PoEdit tidak mendukung operasi pencarian & menggantikan teks sekaligus. Cara lainnya bisa dilakukan dengan membuka messages.po file dalam editor teks yang umum dan melakukan pencarian & ganti di file tersebut. Daftar berikut akan membantu untuk mengatasi situasi ini. 

• Daftar kata-kata / frasa umum di Senayan:

– Ini hanyalah sebuah daftar kecil dengan kata-kata / frase terjemahan yang ditemukan dalam menterjemahkan. Daftar ini dapat membantu untuk menemukan terjemahan istilah yang paling "menyusahkan" dan menjaga konsistensi penggunaan sinonim dalam menterjemahkan.







1.7 Setting Barcode

Untuk mendapatkan hasil pencetakan barcode yang bagus, minimal karakter barcode adalah 6, yang bisa terdiri dari angka atau huruf. Hindari *&()%$#@!, kecuali (-).

Beberapa contoh pencetakan barcode:







*) pada kartu anggota, panjang nama anggota akan mengakibatkan ID, Nama dan Tipe Anggota menjadi turun (merusak tampilan). Untuk mengatasi hal ini, sesuaikan panjang nama anggotanya dan panjang kartu anggota.



1.8 Merubah Template OPAC

Untuk mendapatkan tampilan yang berbeda dari tampilan standar OPAC pengguna dapat melakukan perubahan pada template yang telah disediakan di dalam distribusi SLiMS. Berikut adalah tampilan standar SLiMS



Isi dari tampilan di atas dapat dilihat di dalam folder /template/default.

\vskip 1em

Gambar-gambar yang berada pada template yang ditampilkan di atas, semuanya terdapat di dalam folder /template/default/media. Semua komponen gambar yang ada seperti logo, gambar latar tinggal diganti menggunakan logo dan gambar latar yang Anda inginkan.

\vskip 1em

Harap diingat, bahwa penamaan file gambar latar atau logo yang baru harus sama dengan nama file gambar latar atau logo sebelumnya. Apabila Anda tidak melakukan perubahan nama untuk file logo, gambar latar dan lainnya, yang harus Anda lakukan adalah menyunting file style.css yang folder /template/default. Rubah bagian-bagian yang mengindikasikan nama-nama file logo, gambar latar dan lainnya.



1.9 Mengaktifkan Apache dan MySQL pada psenayan sebagai service otomatis di Microsoft Windows

Apache web server dan basisdata MySQL pada portable senayan yang digunakan oleh sistem operasi Microsoft Windows dapat dijalankan secara otomatis, tanpa harus mengaktifkan file apache_start.bat dan mysql_start.bat secara manual, dengan cara membuat kedua file tersebut menjadi service.

\vskip 1em

Kita mulai dengan membuka command prompt pada Windows. Untuk menjadikan Apache web server sebagai service, pastikan kita sudah berada dalam direktori psenayan. Masukkan perintah:

\psenayan\apache\bin\httpd.exe -k install -n Apache2.2

Sebagai contoh, apabila psenayan kita letakkan pada drive D:, maka perintahnya adalah:

D:\psenayan\apache\bin> httpd.exe -k install -n Apache2.2 

Perintah di atas menjadikan Apache web server termula secara otomatis ketika Windows dinyalakan.

\vskip 1em

Setelah Apache web server, langkah berikutnya adalah mengatur database MySQL pada portable senayan sebagai service. Sama seperti proses sebelumnya, pastikan kita sudah berada dalam direktori psenayan. Masukkan perintah:

<nama direktori>:\psenayan\mysql\bin\mysqld.exe –install

Sebagai contoh, apabila psenayan kita letakkan pada drive D:, maka perintahnya adalah:

D:\psenayan\mysql\bin> mysqld.exe --install

Perintah di atas telah mengaktifkan MySQL sebagai service. Langkah selanjutnya adalah dengan mengubah beberapa bagian pada file my.ini yang terletak dalam direktori psenayan\mysql. Kita harus merubah basedir serta datadir yang ada. Bagian tersebut adalah:

# set basedir to your installation path 

basedir=/psenayan/mysql 

# set datadir to the location of your data directory 

datadir=/psenayan/mysql/data



Yang harus dirubah adalah penambahan direktori tempat psenayan disimpan pada basedir dan datadir. Karena pada contoh kita menempatkan direktori psenayan pada drive D:, maka bentuk perubahannya:

# set basedir to your installation path 

basedir=D:/psenayan/mysql 

# set datadir to the location of your data directory 

datadir=D:/psenayan/mysql/data

Simpan dan mula ulang komputer Anda. Apabila dalam proses tidak ada kesalahan, maka psenayan langsung bisa digunakan tanpa harus mengaktifkan file apache_start.bat dan mysql_start.bat lagi.

1.10 Menonaktifkan service Apache dan MySQL pada psenayan di Microsoft Windows

Karena satu dan lain hal, mungkin ada kalanya kita ingin menghapus layanan otomatis yang telah kita atur. Untuk itu, apabila kita ingin menghapus layanan Apache maka, pertama-tama, pastikan kita sudah berada pada direktori tempat service Apache berada

D:\psenayan\apache\bin> htppd.exe -k uninstall -n Apache2.2

sedangkan apabila kita ingin menghapus layanan MySQL, sama seperti layanan Apache, pastikan kita sudah berada pada direktory tempat service MySQL berada

D:\psenayan\apache\bin> mysqld.exe --remove

1.11 Jika Kehilangan Password admin pada aplikasi Senayan

Jika pustakawan lupa password admin pada aplikasi Senayan, maka jalan keluarnya adalah merubah ulang password admin melalui database mysql. Langkahnya adalah sebagai berikut:

• Buka phpmyadmin, jika anda menggunakan Psenayan, ketikkan http://localhost/pma kemudian masuk dengan username root dan password psenayan. Maka akan muncul tampilan phpmyadmin.

• Cari database yang anda gunakan di sebelah kiri. Jika belum dirubah maka databasenya adalah senayandb

• Klik tabel user, tabel ini berisi username dan password yang digunakan untuk masuk dalam aplikasi senayan. Nah disinilah tempat dirubahnya password admin.

• Setelah klik tabel user, maka di sebelah kanan akan muncul daftar username yang dimiliki oleh aplikasi Senayan. Klik tanda pena (edit) pada username admin (bernilai 1).





• Ubah password yang telah terenkripsi dengan password baru, misalnya admin



• Pada Function pilih MD5, lalu klik Go.



• Password untuk username admin anda telah tergantikan dengan admin. Silakan masuk ke aplikasi Senayan dengan username admin dan password admin.

1.12 Menambah jenis ekstensi file yang dapat diunggah pada lampiran bibliografi

Ketika mengisi data bibliografi, akan ditemukan fasilitas untuk mengunggah file gambar dan file attachment (lampiran). File gambar ada bermacam-macam, demikian pula file dokumen yang akan diunggah.

JIka anda mengunggah file dan gagal, salah satu kemungkinan (ingat hanya salah satu kemungkinan) adalah ekstensi dokumen/file anda tidak diijinkan diunggah. Misalnya, file berekstensi .WAV. Maka anda bisa melakukan penambahan ekstensi ini agar dapat diunggah. 

• Buka file sysconfig.inc.php

• Cari baris ke (sekitar) 251, maka anda akan mendapatkan kelompok isian sebagai berikut:

$sysconf['max_image_upload'] = 500; // allowed image file to upload $sysconf['allowed_images'] = array('.jpeg', '.jpg', '.gif', '.png', '.JPEG', '.JPG', '.GIF', '.PNG'); // allowed file attachment to upload $sysconf['allowed_file_att'] = array('.pdf', '.rtf', '.txt', '.odt', '.odp', '.ods', '.doc', '.xls', '.ppt', '.avi', '.mpeg', '.mp4', '.flv', '.mvk', '.jpg', '.jpeg', '.png', '.gif', '.ogg', '.mp3');

Anda dapat menambahkan jenis file yang anda maksudkan dalam kode di atas.

Ekstensi file yang tertulis di sini bersifat case sensitif, jadi .mp3 akan berbeda dengan .MP3. Jika dalam sysconfig diijinkan .jpg, dan file anda .JPG maka proses unggah tidak akan berhasil.

Catatan: kegagalan proses unggah juga dipengaruhi oleh hak akses folder image dan repository. Pastikan kedua folder tersebut (jika menggunakan Linux) hak aksesnya 777.

1.13 Mensetting Email server

Dalam Senayan3-stable15 terdapat fitur baru untuk mengirimkan email peringatan/tagihan pada peminjam yang terlambat mengembalikan. Penggunaan fitur ini membutuhkan akun Google/Gmail, karena akan menggunakan fasilitas smpt dari gmail. Seting yang dibutuhkan adalah sebagaimana gambar dibawah ini:



Seting diatas ada dalam file sysconfig.inc.php. Atau jika anda mau, anda bisa mengcopy setingan Mailing Setting ini ke sysconfig.local.inc.php.

Bagaimana penggunaannya? Penggunaan fitur email ini ada pada menu Sirkulasi. Ketika memulai sirkulasi (ID anggota dimasukkan), jika anggota tersebut mempunyai pinjaman yang terlambat, maka tampilan yang muncul adalah sebagai berikut:



Kirim email dengan mengklik "Kirim surel tentang informasi keterlambatan", jika berhasil maka akan ada tampilan/tulisan tambahan diatasnya sebagaimana gambar berikut:



Selain di menu Mulai Sirkulasi, kita juga dapat menggunakan fitur kirim email ini lewat menu "Keterlambatan", baik yang ada pada Modul Sirkulasi maupun Pelaporan. Untuk mengirimkan email, cukup klik "Send Notification E-mail" pada tiap-tiap anggota yang dikehendaki.



Jika anggota perpustakaan membuka emailnya, maka akan ditemukan email yang dikirimkan lewat sistem SLiMS tersebut. Contoh gambarnya adalah sebagai berikut:





1.14 Menambah Captcha 

Mulai Senayan3-Stable15 (Matoa), ada penambahan fasilitas pengamanan login pada login pustakawan dan member.

Captcha ini ada dua, untuk Librarian Login dan untuk Member Login. Untuk mengaktifkan captcha tersebut, perlu diseting pada file sysconfig.inc.php. 





Untuk mengaktifkan, cukup diganti false menjadi true. Maka ketika login akan menemukan tampilan sebagai berikut:





1.15 Menambah Server Z.39.50

Mulai Senayan3-stable15 (Matoa), pengguna SLiMS dimudahkan jika ingin menambahkan tujuan z.39.50 baru. Syarat penggunaan z39.50 adalah terhubung ke internet, dan port yang dibutuhkan terbuka. Sebagaimana diketahui, sebelumnya z39.50 di SLiMS hanya menuju ke Library of Congress Amerika. Bagaimana menambahkannya?

1. Buka situs http://irspy.indexdata.com/, pada situs ini anda dapat menemukan berbagai alamat perpustakaan yang menyediakan server z39.50 untuk saling menukar data. Alamat tersebut dikumpulkan berdasar abjad. Alamat yang akan digunakan adalah perpaduan antara Host, Port dan DB. Misalnya, pada web di atas ada Abertay Dundee University, dibaris yang sama diikuti dengan keterangan Host=catalogue.abertay.ac.uk, Port=10790 dan DB= Voyager. Maka alamat yang nanti kita masukkan dalam setting adalah: catalogue.abertay.ac.uk:10790/Voyager

2. Buka file sysconfig.local.inc.php, kemudian tambahkan code berikut:

$sysconf['z3950_max_result'] = 50; 

$sysconf['z3950_source'][1] = array('uri' => 'z3950.loc.gov:7090/voyager', 'name' => 'Library of Congress Voyager');

Dua baris kode diatas anda dapat memperoleh dengan copy-paste dari file sysconfig.inc.php pada baris 321 dan 322. Baris pertama merupakan pengaturan jumlah record ditampilkan per halaman, sedang baris kedua adalah pengaturan alamat server z39.50.

Setelah itu, tambahkan baris baru (dibawahnya) yang memuat identitas server tujuan z39.50 yang baru, sebagaimana contoh pada nomor 1 di atas (Perpustakaan Abertay Dundee University)

$sysconf['z3950_source'][2] = array('uri' => 'catalogue.abertay.ac.uk:10790/Voyager', 'name' => 'Abertay Dundee University');

3. Selesai, Simpan dan cek di bagian Bibliografi, z39.50 server.

4. Catatan: port yang disyaratkan oleh server z39.50 harus dibuka. Misalnya pada contoh di atas adalah port 10790, untuk bagian ini jika mengalami kesulitas silakan hubungi administrator jaringan di perpustakaan anda. 