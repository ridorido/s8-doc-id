# Second Chapter

1 Bibliography

Libraries are not made; they grow. - Augustine Birrell

Modul ini berisi menu Add New Bibliography (membuat data bibliografi/katalog baru), Bibliographic List (melihat daftar bibliografi), Item List (melihat daftar item/kopi koleksi), Chekout Items (melihat daftar item yang sedang dipinjam). Selain itu, pada modul ini juga dilengkapi dengan copy cataloging, label printing, item barcode printing, import data, eksport data, item import, item eksport. Untuk melihat daftar bibliografi dilakukan dengan klik pada navigasi Bibliography List, demikian pula jika kita ingin melihat daftar item klik pada Item List, melihat Item yang sedang dipinjam klik pada menu Checkout Items. 

1.1 Menu Add New Bibliography 

Menu ini digunakan untuk menambah bibliografi baru, klik pada Add New Bibliography. Maka akan muncul layar seperti dibawah ini: 



Metadata yang harus kita isikan adalah: 

• Title : Judul koleksi 

• Statement of Responbility: Pernyataan tanggungjawab, untuk lebih jelasnya silakan membuka lagi referensi tentang katalogisasi.

• Edition : Pernyataan edisi 

• Specific Detail Info: Berisi informasi khusus bibliografi, misalnya: skala pada peta, catatan serial yang dimiliki.

• Item(s) Code Batch Generator:

Bagian ini diisikan dengan Pola/Pattern, From dan To. Pola berisi pola kode item/barcode yang diinginkan, misalnya B01, From diisi dengan 1, To diisi 10. Hal ini berarti pustakawan menginginkan kode item yang dihasilkan adalah B011, B012 ..... B0110. Model ini akan membantu perpustakaan yang sering menerima koleksi buku paket dalam jumlah banyak, misalnya perpustakaan sekolah.

Jika pola diisi B00, From di isi 1, to diisi 5 maka hasilnya akan menjadi B01,B02,B03,B04,B05.

Namun demikian, anda tetap dapat menggunakan tombol “Tambah Eksemplar Baru” untuk membuat data item baru.

• Author : Kepengarangan 

• GMD : General Material Designation 

• Frequency: Frekuensi terbitan berkala, isian ini mengambil data dari Master File. Jika field ini diisi, maka data bibliografinya akan terdeteksi sebagai serial dan muncul di modul serial control.

• ISBN/ISSN : Nomor ISBN atau ISSN 

• Class : Nomor klasifikasi koleksi (DDC, UDC atau lainnya). Class ini akan sangat berguna dalam proses Stock Take. 

• Publisher : Nama Penerbit, diambilkan dari data yang ada pada Master File

• Publish Year : Tahun Terbit 

• Publication Place : Tempat Terbit 

• Collation : Kolasi/Deskripsi Fisik 

• Series Title : Judul seri (jika ada) 

• Call Number : Nomor Panggil Koleksi 

• Topics : Topic/subyek. Data ini juga dapat diambil dari Master File 

• Classification: Merupakan fitur untuk mengambil nomor kelas dari master file. 



• Language : Pilihan bahasa dokumen 

• Abstract/Notes : Catatan penting berkaitan dengan bibliografi 

• Image : Gambar (biasanya sampul) yang menunjukkan identitas koleksi. Gambar ini akan muncul di OPAC File 

Mulai SLiMS Cendana, terdapat fitur tambahan yaitu scan cover yang dapat langsung disimpan di SLiMS. Fitur ini dapat digunakan dengan syarat diaktifkan terlebih dahulu dan terdapat koneksi ke mesin scanner.

Aktivasi fitur ini adalah dengan merubah value false ke true pada baris $sysconf['scanner'] = true; yang terdapat pada file sysconfig.inc.php (disarankan untuk melakukan perubahan lokal di sysconfig.local.inc.php) 



• Attachment : Dapat diisi dengan file yang berkaitan dengan koleksi (misalnya hasil scan halaman daftar isi koleksi bersangkutan), atau file multimedia dari data bibliografi yang bersangkutan. File yang dapat diupload adalah file yang berekstensi .pdf .rtf .txt .odt .odp .ods .doc .xls .ppt .avi .mpeg .mp4 .flv .mvk .wmv .jpg .jpeg .png .gif .ogg .mp3 .wma .csv. Jika yang diupload adalah file multimedia, maka nantinya senayan akan memutar secara streaming dengan program Flowplayer dan tidak dapat diunduh.  Sedangkan jika file yang diupload adalah file non multimedia, maka file tersebut dapat didownload. (Contoh pemutaran file multimedia ada di bagian OPAC). File yang diupload bisa lebih dari satu file, dan dapat diset Public (dapat dilihat oleh user) atau Private (berdasar jenis keanggotaan). Berikut ketentuan pembatasan akses:

– Pembatasan akses file di senayan berbasiskan group (tipe keanggotaan). Jadi pembatasan akses ini terintegrasi dengan jenis keanggotaan. Tidak bisa pembatasan akses berdasarkan perorangan.

– Ada dua jenis akses dalam akses ke file: "public" dan "private".

– Jika dipilih akses "private" maka file sama sekali tidak bisa diakses oleh siapa pun.

– Jika file dipilih akses "public" dan tidak dicek group mana saja yang bisa mengakses, maka file bisa didownload oleh semua orang.

– Jika file dipilih akses "public" dan dicek group mana saja yang bisa mengakses, maka file bisa didownload hanya oleh anggota yang telah melakukan login dan terdaftar dalam group tersebut.



Untuk menambahi jenis file yang dapat diunggah, silahkan membaca pada bagian tips dan trik.

• Hide in OPAC: 

– Show: Data Bibliografi bisa diakses melalui OPAC.

– Hide: Data Bibliografi tidak dapat diakses melalui OPAC

• Promote in Homepage: untuk mengatur sebuah bibliografi, apakah akan ditampilkan di halaman depan atau tidak. 

• Label: Untuk memberikan informasi khusus tentang bibliografi. label dapat didefinisikan pada menu Master File. Secara default Senayan mempunyai tiga label: New Title, Favorite Title dan Multimedia.

Fitur Promote to Homepage  berkaitan dengan konfigurasi Show Promoted Titles at Homepage yang ada pada Modul System Configuration. Sedangkan Label harus didefinisikan di Master File dulu. Pada label, dapat diisikan URL yang sesuai dengan bibliografi.



Setelah data kita isikan, klik Save. Jika berhasil maka sistem akan memunculkan informasi bahwa data bibliografi, file dan gambar telah sukses di simpan. Layar tidak akan berganti, namun akan bertambah. Tambahannya adalah hasil generate item sesuai dengan yang diisikan. Letaknya dibawah Specific Detail Info. 



Tugas berikutnya adalah mengedit kode item dan memasukkan identitas item sesuai dengan item yang diterima. Kode item merupakan kode unik yang mewakili tiap eksemplar koleksi. Jika setelah input item ternyata ada item baru lagi, dapat ditambahkan dengan cara klik pada Add New Item, maka akan muncul pop-up window seperti gambar berikut ini : 



Form penambahan item ini berisi field sebagai berikut: 

• Title 

• Item code 

• Call Number

• Inventory Code (Kode Inventaris) 

• Location (mengacu pada Master File) 

• Shelf Location

• Collection Type 

• Item Status 

• Order Number 

• Order Date 

• Received Date 

• Supplier 

• Item Source 

• Invoice 

• Invoice Date 

• Price 

1.2 Menu Bibliographic List 

Menu ini digunakan untuk melihat data bibliografi yang sudah ada dalam database Senayan. Informasi yang dimunculkan dalam menu ini adalah: Title, pengarang, ISBN/ISSN, Copies dan Last Update. Menu ini memungkinkan kita untuk dapat mengurutkan daftar berdasar title/judul, ISSN/ISBN, copies dan juga last update. Dengan menu ini pula, bibliografi dapat dicari untuk di edit atau di hapus. Berikut langkah untuk mengedit atau menghapus bibliografi lewat menu Bibliographic List: 

• Cari bibliografi yang akan diubah dengan mengetikkan judul pada Search Bibliografi, pilih field kemudian klik Search 

• Setelah ditemukan, check box data yang akan di hapus lalu klik Delete Selected Data atau klik icon edit (sebelah kiri judul) untuk mengedit . 

• Muncul tampilan data bibliografi yang masih di disable. 

• Aktifkan mode edit dengan klik icon Edit di pojok kanan bawah atau pojok kanan atas. 

• Edit bagian yang perlu, kemudian klik Save Change. 





1.3 Menu Item List 

Menu ini digunakan untuk melihat item yang dalam database Senayan. Informasi yang ada dalam menu ini adalah: Item Code, Title, Type, Location, Class, dan Last Update. Dengan menu ini dapat pula dilakukan proses edit dan hapus item. Berikut langkah untuk mengedit atau menghapus item: 

• Cari item yang akan diubah/hapus dengan mengetikkan judul atau item code pada kolom Search, kemudian klik Search 

• Setelah ditemukan, check box data yang akan di hapus lalu klik Delete Selected Data atau klik icon edit (sebelah kiri judul) untuk mengedit . 

• Muncul tampilan data item yang masih di disable. Aktifkan mode edit dengan klik icon Edit di pojok kanan bawah atau pojok kanan atas. 

• Edit bagian yang perlu, kemudian klik Save Change.





1.4 Menu Checkout Items 

Menu ini memberikan informasi tentang item yang sedang dipinjam. Dalam menu ini dilengkapi juga dengan fasilitas pencarian dengan pendekatan item dan judul bibliografi. Informasi yang ada dalam menu ini adalah Item Code, Member ID peminjam, Title, Loan Date (tanggal pinjam), Due Date (tanggal kembali). 



1.5 Copy Cataloging

Copy cataloging pada SLiMS mengoptimalkan 3 layanan tukar menukar data. Z39.50 SRU dengan memanfaatkan xml yang berformat MODS, Z 39.50 yang memanfaatkan YAZ serta P2P service yang memanfaatkan XML antar SLiMS.

1.5.1 Z 39.50 SRU: Search/Retrieval via URL

Merupakan fitur yang digunakan untuk proses copycataloging sebagaimana pada Z 39.50 Service. Perbedaan dari sisi pengguna, penggunaan SRU tidak mensyaratkan instalasi YAZ.



1.5.2 Z 39.50 Service

Merupakan fitur baru di SLiMS mulai stable-10, dimana memungkinkan perpustakaan pengguna senayan untuk mengambil koleksi dari perpustakaan berbagai perpustakaan. Secara default SLiMS mengarah ke Library of Congress (http://loc.gov), namun dapat ditambahi sesuka kita. Pustakawan cukup memasukkan judul, pengarang atau ISBN/ISSN, kemudian Senayan akan mengambil data. Jika hasilnya lebih dari satu, maka pustakawan dimungkinkan untuk memilih koleksi yang diinginkan kemudian save.

Untuk efektifitas penggunaan Z39.50 dapat digunakan ISBN/ISSN, karena dengan ISBN/ISSN pencarian koleksi bisa lebih akurat. 









Untuk penggunaan Z39.50 library YAZ harus diinstall terlebih dahulu. Detail installasi YAZ, bisa dibuka di http://dicarve.blogspot.com. Sedangkan pada Psenayan YAZ sudah dipaketkan. Selain YAZ, port yang dibutuhkan juga harus terbuka. Detail url yang menyediakan protokol Z39.50 dapat dilihat di http://irspy.indexdata.com/. Selain ke perpustakaan-perpustakaan tersebut, SLiMS juga dapat mengambil data (copycataloging) dengan menggunakan protokol z39.50 ke aplikasi lain, misalnya KOHA. 

1.5.3 Menu P2P Service

P2P Service merupakan fitur baru yang ada mulai Senayan3Stable14. Konsep dasar dari fitur ini adalah berbagi data bibliografi antar pengguna Senayan. P2P Service memanfaatkan fasilitas xml yang telah ada di senayan untuk berbagi koleksi bibligrafi. Untuk penggunaan P2P Service ini, cukup dengan klik p2p service, isikan kata kunci dan pilih lokasi/url/perpustakaan yang dituju untuk pencarian. Jika sistem menemukan koleksi yang dicari, maka akan ditampilkan.

Pencarian pada P2P Service ini dapat menggunakan pencarian spesifik model Boolean. Sebagai contoh isbn=0-596-00108-8 AND title=bazaar. Selain ISBN dan Title, pencarian detail dapat juga menggunakan author, GMD dan subject. 



P2P dapat dikonfigurasi melalui perubahan pada file sysconfig.inc.php sebagaimana contoh berikut:

Cari baris seperti di bawah ini,

$sysconf['p2pserver'][1] = array('uri' => 'http://127.0.0.1/senayan3-stable14', 'name' => 'SLiMS Library');

Kemudian edit sesuai dengan alamat dan nama Perpustakaan yang dituju. P2P dapat juga membaca dirinya sendiri. Jika ada lebih dari satu alamat yang dituju, maka dapat ditambahkan baris di bawahnya, sebagaimana contoh berikut:

$sysconf['p2pserver'][1] = array('uri' => 'http://127.0.0.1/slims', 'name' => 'SLiMS Library');

Alamat OPAC Senayan yang hendak diambil datanya menggunakan P2P haruslah mengaktifkan fitur xml. Fitur ini dapat diaktifkan dalam modul System. P2P hanya bisa dilakukan pada Senayan mulai stable-13.

1.6 Menu Labels Printing 

Dengan menu ini kita dapat mencetak label koleksi berdasar data bibliografi yang sudah dimasukkan dalam SLiMS. Berikut urutan mencetak label menggunakan menu Labels Printing: 

• Klik Labels Printing, maka akan muncul tampilan sebagai berikut: 



• Pilih bibliografi yang akan dicetak labelnya. Gunakan tombol Shift+klik kotak chek box untuk memilih lebih dari satu secara berurutan dengan cepat. Catatan: sekali cetak maksimal 50 data. Dalam menu label print ini, sudah dimungkinkan untuk mencetak label lebih dari satu, tergantung pada berapa jumlah eksemplar koleksi. 

• Klik Add to Print Queue untuk memasukkan pilihan ke dalam antrian cetak. 

• Klik Print Selected Data untuk mulai mencetak, maka akan muncul pop-up yang meminta kita untuk mencetak label kedalam printer. 



Label juga dapat diseting ukuranya melalui fitur seting label:





1.7 Menu Item Barcodes Printing 

Menu ini sebagai sarana mencetak barcode berdasar data item yang sudah dimasukkan dalam SLiMS. Berikut urutan mencetak barcode menggunakan menu Item Barcodes Printing: 

• Klik Item Barcode Printing, maka akan muncul tampilan sebagai berikut: 



• Pilih item yang akan dicetak. Gunakan tombol Shift+klik kotak check box untuk memilih lebih dari satu secara berurutan dengan cepat. Catatan: sekali cetak maksimal 50 data. 

• Klik Add to Print Queue untuk memasukkan ke antrian cetak. 

• Klik Print Selected Data untuk mulai mencetak. maka akan muncul pop-up yang meminta kita untuk mencetak. 





Barcode juga dapat disetting ukurannya melalui fitur seting barcode





1.8 Catalog Print

Fitur ini dapat digunakan untuk mencetak kartu katalog. Cara mencetak hampir sama dengan cara mencetak barcode atau label buku. Hasil dari pencetakan adalah sebagaimana gambar dibawah ini:



1.9 MARC Import

Fitur ini digunakan untuk mengimport data MARC baik itu berekstensi .mrc ataupun .xml. Sebelum menggunakan fitur ini, syaratnya pada server SLiMS telah terinstall PEAR, FILE_MARC dan Structures_LinkedList. Pada server yang menggunakan linux Ubuntu, dapat menggunakan perintah berikut:

sudo pear install channel://pear.php.net/Structures_LinkedList-0.2.2

channel://pear.php.net/File_MARC-0.6.2

Jika belum terinstall, maka tampilan fitur ini adalah sebagai berikut:



Jika sudah terinstall, maka yang tampil adalah:



Jika anda mempunyai berkas MARC, misalnya .mrc (jika anda tidak memiliki, anda dapat mengunduh contoh file Marc berekstensi .mrc di http://www.gale.cengage.com/marc_records/) anda dapat memrosesnya dengan klik BROWSE dan pilih file yang hendak diimport. Number of Record to import berarti berapa jumlah records yang akan di import, 0 berarti semua record yang ada dalam file database. Jika berhasil, maka sistem akan menampilkan tampilan sebagai berikut:



1.10 Menu Import Data 

Menu import data ini digunakan untuk mengambil data bibliografi dari luar SLiMS dalam format csv (atau dari database Senayan yang sudah di eksport dalam bentuk .csv), kemudian dimasukkan dalam program aplikasi Senayan. 

Untuk petunjuk import data, secara lebih detail silakan baca pada manual konversi data dari Athenaeum ke Senayan dan dari SIPISIS ke Senayan. Manual konversi ini dapat anda peroleh di http://slims.web.id/download/docs/tutorial-athen2senayan.pdf dan http://slims.web.id/download/docs/tutorial-isis2senayan.pdf

Selain itu Tim Pengembang Senayan juga menyediakan tool online untuk konversi senayan. Tool ini dapat anda akses di http://slims.web.id/senayan-converter/

1.11 Menu Export Data 

Menu export data ini digunakan untuk mengambil data bibliografi dalam aplikasi Senayan, untuk kemudian dapat di masukkan dalam aplikasi senayan lainnya. Proses ini dapat dipahami sebagai pertukaran data.

Proses eksport akan menghasilkan file .csv, sedangkan proses import membutuhkan file dengan format .cvs. Format .csv tersebut adalah berurutan sebagai berikut: Title, GMD, Edisi, ISBN, Publisher, Thn Terbit, Deskripsi Fisik, Judul Seri, Call Number, Bahasa, Tempat Terbit, Klasifikasi, Catatan, nama file Image, nama file File attachment, pengarang, subyek, barcode.

Contohnya adalah sebagai berikut: 

"Corruption and development","Text","","9780714649023","Taylor &Francis Inc.","1998","166 p. : ill. ; 22 cm.","","364.1 Rob c","English","London","364.1/322/091724 21","The articles assembled in this volume offer a fresh approach to analysing the problem of corruption in developing countries and the k means to tackle the phenomenon.","corruption_development.jpg","","<Robinson,Mark>","Corruption><Development>","<B00006>"

Dalam proses Eksport terdapat form pilihan: 



Keterangan: 

• Field Separator : untuk mendefinisikan pemisah antar field 

• Field Enclosed with : mendifinisikan karakter pembuka/penutup 

• Field Record Separator : Pemisah antar Record 

• Number of Record to Export: Jumlah Record yang di Eksport 

• Start From Record: Record pertama Proses Export dimulai 



Keterangan: 

• File To Import : File yang akan di import, berekstensi .csv dan sesuai dengan format .csv yang digunakan senayan (lihat contoh diatas) 

• Field Separator: Pemisah antar field yang digunakan 

• Field Enclosed with: Karakter pembuka/penutup field 

• Number of Record to Import: Jumlah Record yang akan diimport 

• Start from record: Record pertama Proses Import dimulai 

1.12 Item Eksport

Format hasil eksport data item pada SLiMS adalah sebagai berikut:

"B00001","","Reference","INV/B00001","0000-00-00","","","MyLibrary","0000-00-00","","","1","","500000","Rupiah","0000-00-00",

"2008-12-26 22:11:10","2008-12-26 22:14:13","Ajax : creating Web pages with asynchronous JavaScript and XML"

Format diatas daat dijadikan acuan jika ingin memasukkan data .csv ke SLiMS. Caranya adalah dengan menyesuaikan format .csvnya.

1.13 Item Import

Item import digunakan untuk memasukkan data item ke database SLiMS. Jika kegiatan ini dilakukan dari database SLiMS yang satu ke SLiMS yang lain, maka item import dilakukan setelah bibliography import. Artinya item akan menyesuaikan data bibliografi yang telah diimport lebih dahulu. 

1.14 Biblio Custom Field

Fitur ini digunakan untuk menambahkan Field baru pada Bibliografi, dimana field ini dibutuhkan oleh perpustakaan yang menggunakan Senayan namun belum tersedia dalam field standard SLiMS. 

Untuk menambahkan field baru dilakukan langkah sebagai berikut:

• Buka file custom_fields.inc.php yang terletak pada folder admin/modul/bibliography

• Dalam file ini tersedia lima (5) Custom Field yang dapat digunakan, jika hanya ingin menambah satu saja, maka 2-5 dapat dihapus.

• Berikutnya anda harus merubah sesuai dengan kebutuhan field perpustakaan anda, misalnya kita mau menambahkan nama penginput data, maka (misalnya):

'dbfield' => 'librarian', // name of field in 'biblio' table in database, make sure you already define it! 

'label' => __('Librarian'), // label of field in form 

'type' => 'text', // type of field 

'default' => '', // default value of field 

'max' => '50', // maximum character to enter in 'text' field type

'data' => false, // an array of data for 'dropdown', 'checklist' or 'choice'

'indexed' => true, // NOT APPLICABLE YET, FOR FUTURE RELEASE USE

'width' => 50), // width of field in form for 'text' field type, maximum is 100

• Langkah berikutnya adalah membuat field librarian pada tabel biblio_custom. Tabel biblio custom sudah ada jika kita menginstall minimal Senayan3-stable14 (Seulanga), atau akan terbuat jika dilakukan upgrade SLiMS ke senayan3-stable14

• Hasil dari penambahan field tersebut ada pada tampilan Add New Bibliography

