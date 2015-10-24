# First Chapter

# First Chapter
1 Instalasi

SLiMS mempunyai beberapa cara instalasi. Instalasi dari source code (dengan editing manual untuk nama database, username dan password), instalasi psenayan (portable senayan), dan instalasi dengan menggunakan SLiMS Installer. Berikut penjelasan dari masing-masing cara instalasi tersebut. Meskipun contoh yang digunakan menggunakan SLiMS versi lama, namun pada dasarnya sama untuk SLiMS versi berikutnya. 

1.1 Instalasi SLiMS dari source

Education is the passport to the future, for tomorrow belongs to those who prepare for it today (Malcolm X)

Mulai Stable15 (Matoa) setelah senayan selesai install, database harus diindex terlebih dahulu, untuk cara index terdapat pada bagian Modul System)

Pastikan Web Server (misalnya Apache web server), MySQL database server, dan PHP scripting engine telah terinstall dan berjalan dengan baik. Akan lebih mudah lagi kalau PhpMyAdmin juga diinstal karena akan sangat membantu setup database via interface web. Jika anda menggunakan Windows, direkomendasikan menggunakan portable Senayan for Windows yang sudah terbukti stabil untuk SLiMS dan mudah diinstal dan di backup (cukup kopi folder).

Instalasi SLiMS dari source lebih direkomendasikan untuk platform selain Windows seperti GNU/Linux dan Unix karena pada platform tersebut kondisinya relatif lebih beragam. Di Unix/Linux, instalasi Web server (misal Apache), MySQL dan PHP bisa dilakukan melalui paket binary bawaan distro masing-masing. Atau instalasi dari source code yang menawarkan fleksibilitas.

SLiMS dikembangkan pada platform GNU/Linux (Zenwalk dan Ubuntu) dan sudah dicoba dalam skala produksi di beberapa server yang berbasis Centos Linux, OpenSUSE Linux, FreeBSD dan Windows. Pada dasarnya tidak ada masalah dengan Operating System yang digunakan. Yang penting PHP dan MySQL sudah berjalan dengan baik pada Operating System tersebut. Jika Senayan digunakan di internet (publik), disarankan untuk meningkatkan keamanan dengan menambahkan firewall di sisi TCP/IP (layer 3 dan 4 dari OSI layer), di sisi aplikasi (contoh modsecurity ) dan di sisi database (contoh greensql: ). Tutorial implementasinya bisa dibaca di: http://hendrowicaksono.multiply.com/journal/item/54



Sekarang letakkan source SLiMS pada web document root web server yang anda gunakan. Contoh: saya menggunakan Ubuntu Linux dan menginstall Apache Webserver dari source code, web document root nya terletak di /usr/local/apache/htdocs. Sedangkan di OpenSUSE terletak di /srv/www. Jika anda menggunakan xampplite, web document root biasanya terletak pada \xampplite\htdocs. Masih di Windows, jika anda meng-install Apache satu persatu (bukan melalui paket AMP), web document root biasanya terdapat di Program Files\apachegroup\apache\htdocs





Ekstrak file senayan3-*.tar.gz di direktori yang sama. Pada Windows anda bisa menggunakan Winzip. Pada Linux anda bisa menggunakan tools bawaan Linux. Misalnya (pada Ubuntu yang saya gunakan) dengan menjalankan perintah: 

shell> sudo tar -xvxf senayan3-stable10-patch1.tar.gz 

maka akan terbentuk folder/direktori senayan3-stable10.



Sekarang masuk ke folder senayan3-stable10 yang baru terbentuk.

shell> cd senayan3-stable10

Ada dua file sql yang akan kita masukkan untuk struktur dan data contoh aplikasi senayan. Untuk melihatnya, jalankan perintah: 

shell> ls -la install/*.sql 

Sekarang dengan user yang punya akses untuk membuat database (contoh: root), kemudian buat database dengan nama 'senayandb”: 

shell> mysql -u root -p 

mysql> CREATE DATABASE senayandb; 

mysql> SHOW DATABASES; 

mysql> quit;







Berikutnya membuat struktur data senayan dan meng-instal data sampel. 

shell> mysql -u root -p senayandb < install/senayan.sql 

shell> mysql -u root -p senayandn < install/sample_data.sql







Opsional, dengan alasan keamanan, anda bisa membuat user khusus untuk database senayan. Caranya jalankan perintah berikut: 

shell> mysql -u root -p 

mysql> GRANT ALL PRIVILEGES ON senayandb.* TO 

'senayanuser'@'localhost' IDENTIFIED BY 'password_senayanuser';





Sekarang edit file sysconfig.local.inc.phpMulai Matoa, SLiMS menggunakan sysconfic.local.inc.php sebagai tempat konfigurasi local. Maksudnya, jika ada perubahan, atau konfigurasi baru dalam file sysconfig.local.inc.php, maka yang akan dibaca oleh SLiMS terlebih dahulu adalah file sysconfig.local.inc.php. Atau jika ada dua konfigurasi yang sama pada file sysconfig.local.inc.php dan sysconfig.inc.php maka SLiMS tetap akan membaca pertama di file sysconfig.local.inc.php.  dengan editor favorit anda (misal: notepad, vim), kemudian ubah Database connection config. Jika nama database anda berbeda, ubah nilai dari DB_NAME. Begitu juga dengan DB_USERNAME dan DB_PASSWORD. Simpan perubahannya, kemudian tutup editor anda.

Mulai Senayan3-stable15, jika ingin menginstall SLiMS tidak perlu mengubah konfigurasi pada file sysconfig.inc.php, namun konfigurasi local database dapat dilakukan di sysconfig.local.inc.php. Letak file ini sama dengan letak file sysconfig.inc.php.

Di Unix/Linux, Pastikan Apache web server bisa melakukan aksi tulis ke direktori images dan files. Bisa dengan dua cara. Pertama dengan mengubah hak akses direktori sehingga bisa ditulis (change mode). Sebagai root lakukan: 

shell> chmod -R 777 images 

shell> chmod -R 777 files

shell> chmod -R 777 repository

Cara kedua dengan mengubah kepemilikan user direktori tersebut (anda harus tahu terlebih dahulu user yang menjalankan proses web server. Misalnya user “daemon”, nobody, dan lain-lain). Sebagai root lakukan: 

shell> chown -R daemon images 

shell> chown -R daemon files

shell> chown -R daemon repository



Sekarang coba akses ke http://localhost/namafolderslims/Mulai stable 15 (Matoa) untuk menampilkan data bibliografi di OPAC SLiMS, terlebih dahulu harus dilakukan indexing. Cara index ada pada bagian Modul Sytems.

SLiMS sudah bisa digunakan

0.1 Instalasi Portable Senayan di Windows

Portable Senayan for Windows (Psenayan) adalah paket software yang terdiri dari aplikasi Senayan, Apache Web Server, PHP Scripting engine, MySQL database Server dan PHPMyAdmin, didalamnya library YAZ yang digunakan untuk mengaktifkan fitur copycataloging menggunakan z39.50 sudah terinstall. Psenayan ditujukan agar orang mudah melakukan instalasi SLiMS tanpa dibuat bingung cara menginstall software lain (web server, mysql, php, YAZ) terlebih dahulu. Tinggal copy, ekstrak dan jalankan!



Kopi file psenayan-x.x.zip (misalnya psenayan-3.0.zip, silakan dapatkan rilis terbaru Psenayan di http://slims.web.id) ke root directory. Misalnya ke c:\ atau d:\. Jangan letakkan didalam direktori/folder lain.



Ekstrak file psenayan*.zip langsung ke root directory. Jika anda telah menginstal utiliti untuk ekstrak file terkompresi seperti Winzip atau Winrar, biasanya klik kanan pada file, akan memunculkan opsi “Extract Here”. Pilih opsi tersebut.



Otomatis akan terbentuk folder “psenayan”. Berikutnya masuk ke dalam direktori tersebut.



Sekarang Jalankan file “apache_start.bat” dan “mysql_start.bat”. Pertama jalankan file “apache_start.bat” terlebih dahulu (double-click pada file tersebut).



Pada Windows yang Firewall-nya aktif, biasanya akan muncul pop-up “Windows Security Alert”. Klik tombol “Unblock” untuk mengijinkan komputer menjalankan proses Apache web server.



Jika proses Apache berhasil diaktifkan, akan muncul window dengan pesan “Apache 2 is starting”. Biarkan window tersebut.



Berikutnya aktifkan mysql database server dengan melakukan double-click pada file “mysql_start.bat”. Pada Windows yang Firewall-nya aktif, biasanya akan muncul pop-up “Windows Security Alert”. Klik tombol “Unblock” untuk mengijinkan komputer menjalankan proses Mysql database server.



Jika proses MySQL berhasil diaktifkan, akan muncul jendela dengan pesan “ready for connections”. Biarkan jendela tersebut.

Selain dengan klik dua file tersebut (apache_start.bat dan mysql_start.bat), juga dapat dijalankan dengan dounle klik file psenayan_start.bat saja. File ini mulai ada pada Psenayan-5



Aktifkan browser, kemudian akses http://localhost. Akan muncul tampilan OPAC dari aplikasi Senayan. Sekarang Senayan sudah bisa digunakan. Jika ingin mematikan proses Apache dan MySQL, double-click pada file “apache_stop.bat” dan “mysql_stop.bat”.

Untuk masuk ke dalam menu administrasi, silakan klik “Librarian Login”. Username admin dan password admin. Sedangkan username dan password untuk masuk phpmyadmin di Psenayan adalah: username root password psenayan. Pada Psenayan, url untuk masuk di PhpMyadmin adalah http://localhost/pma

0.1 Instalasi menggunakan Installer

Pada SLiMS Meranti, selain instalasi secara manual (cara pertama) juga dapat dilakukan dengan instalasi menggunakan fitur SLiMS Installer. Langkah penggunaan SLiMS installer ini adalah: 

1. Buat database 

2. Buat username dan password untuk database 

3. Panggil SLiMS dengan webbrowser, misalnya http://localhost/slims-slims5/, maka secara otomatis browser akan mengarakahkan ke http://localhost/slims-slims5/install/index.php. 

Tampilan pada langkah ini adalah sebagai berikut: 



Klik Lets Start Transaction

4. Isikan host, nama database, username dan password yang akan digunakan (sudah dibuat sebelumnya). Serta tentukan apakah akan menginstall data contoh atau tidak. Tampilan isian seperti gambar di bawah ini:



5. Klik Continue, jika berhasil maka akan muncul tampilan sebagai berikut:



Pada keterangan gambar di atas, untuk keamanan silakan hapus folder install.