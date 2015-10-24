# Bab 8

1 System

The library is an arena of possibility, opening both a window into the soul and a door onto the world. --Rita Dove

Modul Systems ini terdiri dari: 

1.1 Menu System Configuration 

Form di sini dapat anda gunakan untuk melakukan pengubahan preferensi global aplikasi Senayan, seperti Library Name, Public Template (tampilan OPAC), Default Application Language, Admin Template (tampilan Admin), Number of Collections to Show in OPAC Result List (jumlah koleksi yang akan ditampilkan pada setiap halaman di OPAC), Show Promoted Titles at Homepage (menampilkan Judul dalam halaman awal), Disable/Enable Quick Return (untuk memperbolehkan pengembalian koleksi dengan metode cepat), Loan Limit Overrride (Pengabaian Batas Pinjam), Disable/Enable detail XML di OPAC, Disable/Enable hasil XML di OPAC, seting Allow (mengijinkan) atau Forbid (melarang) pengunjung/pengguna untuk mengunduh file attachment di OPAC, Session Login Timeout, serta Barcode Encoding. Dalam menu ini pula, kita dapat melihat versi senayan yang kita gunakan.



Fitur Show Promoted Titles at Homepage pada Modul System ini, jika di chek box, maka tampilan depan OPAC akan kosong, kecuali jika ada data bibliografi yang diset untuk di tampilkan pada halaman depan. Lihat menu add new bibliografi pada modul bibliografi.

Mulai Senayan3-stable11, terdapat fitur untuk menentukan tanggal pinjam dan kembali secara manual. Fitur ini dapat diaktifkan melalui Modul System Configuration, bagian Loan and Due Date Manual Change. (Penggunaan fitur ini lihat pada bagian Modul Circulation)

1.2 Menu Content

Menu ini digunakan untuk mengubah tampilan content aplikasi senayan. Secara default, tampilan yang sudah ada dan dapat dimodifikasi dalam menu ini adalah: Homepage info, terletak di bagian depan OPAC -ketika di klik home-. Welcome to admin page, tampilan awal ketika masuk ke menu admin (Senayan Managemen Console). Help on usage, pada OPAC. Library Information, juga ada pada OPAC.









Silakan melihat URL untuk menampilkan content di atas. Terlihat path yang dibuat pada content yang baru yaitu 'pustakawan'. Untuk menampilkan conten dengan path pustakawan ini, maka kita perlu menuliskan url:

http://localhost/senayan3-stable9/index.php?p=pustakawan

Url ini dapat kita buat pada menu di opac dengan mengedit template.

1.3 Menu Biblio Indexes

Menu ini digunakan untuk melakukan index pada database bibliografi yang adalam SLiMS. Dengan adanya proses index ini maka performa pencarian dalam SLiMS dapat meningkat.



Terdapat tiga fungsi pada menu ini:

• Emptying Index untuk mengosongkan hasil index yang sudah ada

• Re-Create Index, untuk membuat ulang index kesemua data bibliografi dalam database

• Update index, untuk melakukan index pada data bibliografi yang belum terindex.

1.4 Menu Modules 

Didalamnya terdiri dari Module List (melihat daftar module), search (mencari module), Edit dan Delete Modul serta Add New Module (menambah module). Untuk menambah module, folder modul yang sudah ada diletakkan dalam folder admin/modules/. Kemudian klik Add New Modules, isikan informasi modul baru, yaitu: Module Name (nama modul), Module Path (path/letak modul), Module Description (deskripsi singkat modul), kemudian klik Save. 





1.5 Menu System User

Merupakan fasilitas untuk menentukan user yang dapat mengakses sistem sesuai dengak haknya masing-masing. User ini nantinya dapat melakukan Login sesuai dengan username dan password-nya masing-masing. Dalam menu ini terdapat beberapa fasilitas: Add New User (menambah user), Users List (melihat daftar user), Search (mencari user), Edit dan delete user. Untuk menambah user baru, klik Add New User, kemudian isikan Login Username, Real Name, Groups, Password. 



1.6 Menu User Groups 

Merupakan fasilitas untuk mendefinisikan Groups dari User. Dalam User Groups ini anda bisa membuat pengelompokan User-user system anda serta memberikan hak baca (Read) atau Tulis (Write) pada modul-modul Senayan. Setiap User pada Senayan bisa bergabung ke lebih dari satu grup. 



1.7 Menu Holiday Setting 

Merupakan fasilitas untuk menentukan hari-hari libur dimana perpustakaan tidak membuka pelayanan. Pendefinisian hari libur ini akan perpengaruh pada perhitungan hari kerja/buka aktif perpustakaan dan perhitungan denda. Ada dua jenis hari libur yang dapat didefinisikan dalam menu ini, hari libur rutin (senin s.d minggu) dan hari libur khusus (didefinisikan dengan tanggal, bulan dan tahun). 





Untuk Set Holiday, pustakawan tinggal memilih hari yang merupakan hari libur rutin. Sedangkan untuk Add Special Holiday, pustakawan dapat menentukan tanggal, bulan , tahun serta keterangan hari libur. Selain itu, special holiday juga dapat diseting dengan kisaran waktu libur (tanggal mulai sampai tanggal selesai libur). 

1.8 Menu Barcode Generator 

Merupakan fasilitas untuk membuat barcode (kode batang). 





Masukkan kode-kode yang akan dibuat menjadi barcode pada kolom-kolom yang ada dilayar. Tentukan ukuran barcode (Small, Medium, atau Big), kemudian klik tombol Generate Barcode. Maka barcode dapat dilihat dalam bentuk .html dan dapat dicetak dalam printer. Default encoding barcode yang digunakan adalah 128B. Anda dapat merubah encoding barcode ini pada file konfigurasi global Senayan, sysconfig.inc.php. Temukan baris yang tertulis:

$sysconf['barcode_encoding'] = '128B';

Ubah nilai 128B menjadi tipe encoding yang anda inginkan. Pastikan direktori images bisa ditulis oleh web server anda. 

Catatan: 

Karakter yang dapat diproses dalam Barcode Generator hanyalah kumpulan angka dan huruf. 

1.9 Menu System Logs 

Merupakan menu untuk melihat rekaman proses yang dilakukan oleh Senayan. Rekaman yang muncul adalah Time (waktu), Location (lokasi -nama modul-), dan Message (keterangan). Message yang muncul dalam System Logs ini meliputi Siapa (User/Administrator), melakukan apa dan dari mana.



Ketika aplikasi Senayan ini sudah lama digunakan, maka secara otomatis log proses kerja Senayan juga akan bertambah banyak. Oleh karena itu, dalam menu System log ini, diberikan fasilitas SAVE LOGS TO FILES. Proses ini akan menyimpan log yang ada, dan kemudian kita bersihkan layar dengan klik CLEAR LOGS. 

1.10 Menu Backup Database 

Merupakan fasilitas untuk membuat cadangan (backup) database Senayan. Untuk dapat membuat cadangan, perlu terlebih dahulu didefinisikan letak/path file mysqldump. Caranya adalah dengan mengedit file sysconfig.inc.php. Cari baris yang tertulis:

$sysconf['mysqldump'] = '/usr/bin/mysqldump';

gantilah /usr/bin/mysqldump sesuai dengan letak mysqldump di komputer server. Setelah path mysqldump tepat, klik Start New Backup maka Senayan akan membuat cadangan secara otomatis. Format file cadangan yang dibuat Senayan adalan .sql dan diberi nama sesuai tanggal pembuatan, misalnya: backup_20080501_123106.sql. Nama file cadangan di atas berarti: dibuat pada tanggal 1 bulan 5 tahun 2008, pada pukul 12:31:06. 

catatan: untuk melakukan backup ini, user database mysql harus mempunyai hak LOCK TABLES