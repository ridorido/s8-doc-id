# Bab 12

1 Union Catalog Server (UCS)

UCS merupakan fitur yang muncul pada Senayan3-Stable14. Ide dasar fitur ini adalah untuk menyatukan koleksi bibliografi dari berbagai katalog perpustakaan yang menggunakan Senayan, sehingga seseorang dapat mencari koleksi hanya melewati satu pintu (tampilan) saja. Hasil temuan akan disajikan lengkap dengan lokasi dimana koleksi itu berada. 



Pada tampilan di atas, penelusur dapat menemukan informasi bibliografi koleksi serta lokasi perpustakaannya. Jika Record Detail di klik, atau dapat pula dengan klik judul maka akan muncul informasi lengkap dari koleksi yang bersangkutan, sebagaimana gambar di bawah ini:



Di bawah judul koleksi terdapat tautan View node catalog data, tautan ini menunjukkan katalog asli dari data yang bersangkutan. 

Fitur pencarian pada OPAC UCS ini tidak jauh berbeda dengan cara penelusuran pada OPAC Senayan.

1.1 Mengaktifkan UCS

Fitur UCS ada di bawah master senayan, pada senayan3-stable14 ada pada /senayan3-stable14/ucs. UCS menggunakan library Simbio yang ada di master Senayan, sehingga ucs tidak bisa diinstall berbeda dari master senayan. Untuk mengaktifkan fitur UCS pada Senayan, dapat dilakukan dengan langkah di bawah ini:

1.1.1 Membuat database UCS

UCS menggunakan database yang berbeda dengan Senayan. Struktur database UCS dapat diinstall dengan mengambil file .sql yang ada di /senayan3-st14/ucs/install/ucs.sql.

1.1.2 Seting file ucsysconfig.inc.php

Pada ucsysconfig.inc.php harus didefinisikan host, port, nama database, username dan password. Pendefinisian ini didasarkan pada database yang dibuat pada pada langkah 1.1.1. File ucsysconfig.inc.php terletak pada /senayan3-st14/ucs/

define('DB_HOST', 'localhost'); 

define('DB_PORT', '3306'); 

define('DB_NAME', 'ucs'); 

define('DB_USERNAME', 'root'); 

define('DB_PASSWORD', 'admin');

1.1.3 Seting file ucnode.inc.php 

Letak dari file ini ada di dalam folder utama Senayan. Ketika di buka (menggunakan notapad, geany, gedit dll) maka akan ada file konfigurasi sebagai berikut:

$ucs['serveraddr'] = 'http://127.0.0.1/senayan3-stable14/ucs'; 

$node['id'] = 'slims-node'; 

$node['password'] = '2325f677e21c1613909c953eb03c57352259cc5d'; // default is s0beautifulday 

$node['name'] = 'SLiMS Library'; // node name

Serveraddr merupakan alamat server dari UCS, pada akhir url tidak boleh ditutup dengan slash “/”, untuk penggunanaan testing lokal di Windows gunakan 127.0.0.1 jangan menggunakan localhost. Id merupakan nama node dari senayan yang bersangkutan. Password merupakan kata kunci yang menghubungkan dengan server UCS. Nama merupakan nama Node, dimana ini nantinya akan menjadi nama identitas dari node yang bersangkutan dan ditampilkan di UCS. Id, Password dan Name dari Node Senayan ini nantinya didaftarkan dan harus sama persis dengan konfigurasi node di file ucserver.inc.php



1.1.4 Seting file ucserver.inc.php

File ini terletak pada /senayan3-st14/ucs/ucserver.inc.php. Pada file ini terdapat dua jenis konfigurasi, yaitu konfigurasi server dan konfigurasi node.

Berikut adalah konfigurasi server:

$sysconf['server'] = array( 

'id' => 'd13205a03e019e5926b910046b676c6c04f20363', 

'name' => $sysconf['library_name'], 

'subname' => $sysconf['library_subname'],

'max_node_all' => 5, // maximum connection to server 

'max_node_conn' => 1 // maximum connection for each node 

);

Konfigurasi node:

$sysconf['node']['slims-node'] = array( 

'id' => 'slims-node', // node id (must be UNIQUE, lowercase and not containing any spaces!)

'name' => 'SLiMS Library', // node name 

'password' => '2325f677e21c1613909c953eb03c57352259cc5d', // this hash created with SHA1 algoritm

'baseurl' => 'http://localhost/senayan3-stable13', // node base URL 

'ip' => '' // IP address of node

); 

1.1.5 Upload data bibliografi dari node

Data bibliografi dapat dikirimkan ke UCS melalui node yang sudah terdaftar. Hal ini dapat dilakukan lewat menu bibliografi.



Pilih data bibliografi yang ingin dimasukkan dalam UCS, lalu klik Upload Selected Bibliographic data to union Catalog Server. Maka data bibliografi yang telah dipilih akan masuk ada UCS.

1.2 Konfiguasi UCS di sysconfig.inc.php

Pada sysconfig.inc.php ada beberapa script yang dapat mengkonfigurasi UCS, script tersebut adalah:

$sysconf['ucs']['enable'] = true; 

$sysconf['ucs']['auto_delete'] = true; 

$sysconf['ucs']['auto_insert'] = true;

Script pertama, jika true akan menampilkan fasilitas Upload Bibliographic data to Union Catalog Server yang muncul di modul Bibliography. Auto Delete, jika diisi true akan mengakibatkan jika ada data yang sudah diupload ke UCS, dan pada Node di hapus, maka data yang telah ada di UCS akan ikut terhapus. Auto Insert mengakibatkan data yang diisikan pada modul bibliography pada Node akan otomatis masuk pada UCS dengan tanpa di Upload. 

1.3 Modul Administrasi UCS

Modul adminitrasi UCS dapat diakses dengan menambahkan url /ucs/index.php?p=login. Standar untuk masuk pada modul ini adalah username admin dan password admin. Maka UCS akan menampilkan modul administrasinya sebagai berikut:



Halaman admin ini digunakan untuk mengelola data yang sudah ada dalam server UCS. Modul dalam UCS ini adalah Bibliography, Master File dan System. 

1.3.1 Bibliography

Bibliography ini digunakan untuk mengelola data bibliografi yang sudah diada di server UCS. Pengelolaan ini adalah meliputi perubahan dan penghapusan. Selain itu pada bibliografi ini juga terdapat fitur export data bibliografi UCS ke format .csv. 

1.3.2 Master File

Master File digunakan untuk mengelola (menambah, menghapus, mengedit) data master file. Data yang dapat diubah adalah: GMD, Publisher, Author, Subject, Place, Doc. Language dan Frequency.

1.3.3 Systems

Pada Systems ini terdapat beberapa fitur, antara lain: System Configuration, Content, Modules, System Users, User Group, Nodes Poll, System Log dan Database Backup.

1.3.3.1 System Configuration

Digunakan untuk mengkonfigurasi nama UCS, nama tambahan UCS, Template, bahasa, jumlah koleksi yang ditampilkan, setingan tampilan XML dan session Timeout.



1.3.3.2 Content

Fitur ini digunakan untuk menambah, mengedit atau menghapus Content yang ada di UCS.



1.3.3.3 Modules

Digunakan untuk menseting modul baru yang ditambahkan pada UCS.



1.3.3.4 System Users

Untuk menambahkan user baru yang diijinkan untuk mengakses halaman administrasi UCS.



1.3.3.5 Users Group

Digunakan untuk menambah, mengedit atau menghapus Group.



1.3.3.6 Nodes Poll

Memberlihatkan aktifitas Node, Ip Node waktu mulai request dan akhir request serta status dari Node.



1.3.3.7 System Log

Menunjukkan rincian aktifitas node yang terhubung pada server UCS. 



1.3.3.8 Database Backup

Digunakan untuk mebuat database cadangan UCS. 

