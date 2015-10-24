# Bab 3

1 Membership

Your library is your portrait. - Holbrook Jackson

Modul Membership digunakan untuk mengelola data anggota. Menu-menu ini terdapat beberapa menu, yaitu: 

1.1 Menu View Member List 

Digunakan untuk melihat anggota yang telah terdaftar dalam sistem. Informasi yang ditampilkan adalah Member ID, Member Name, Membership Type, Email, Last update. Pada daftar ini dilengkapi pula dengan fasilitas DELETE dan EDIT. 



Jika ada anggota yang keanggotaanya telah habis, maka kita dapat memperpanjang dengan mengklik menu EDIT. Perpanjangan masa keanggotaan dapat dilakukan secara otomatis atau manual. Otomatis, dapat kita lakukan dengan checkbox EXTEND maka keanggotaan akan diperpanjang selama waktu yang ditentukan, terhitung dari tanggal perpanjangan. 

Sedangkan secara manual, dapat dilakukan dengan editing Expiry Date.



Selain itu perpanjangan juga dapat dilakukan secara massal. Caranya adalah dengan klik View Expired Member, Checkbox member yang akan di perpanjang, kemudian klik Extend Selected Member(s).





1.2 Add New member

Fasilitas untuk menambahkan data anggota baru ke dalam sistem Senayan. Data anggota yang dimasukkan adalah: Member ID (ID Anggota -barcode/RFID-), Member Name (Nama Lengkap Anggota), Register Date (tanggal mendatar), Expiry Date (tanggal kadaluarsa), Institution (nama institusi, nama kantor atau nama organisasi), Membership Type (Tipe Keanggotaan), Gender (Jenis Kelamin), E-mail, Address (Alamat rumah atau kantor), Postal Code (Kode Pos), Phone Number (Nomor Telepon), Fax Number (Nomor Fax), Personal ID Number (Nomor ID Personal seperti no. KTP), Notes (Catatan singkat), dan Upload Photo (File foto anggota). Dalam Expiry date terdapat Auto Set, maksud dari fasilitas ini, jika auto set di check maka tanggal expired anggota akan dihitung berdasar Membership Type. Namun jika di uncheck, maka Expiry date dapat ditentukan secara manual, dengan memilih tanggal Expirednya. 

Pada form ini pula, disediakan fitur Pending Membership. Jika Pending Membership ini di check, maka anggota yang bersangkutan tidak akan dapat melakukan sirkulasi, meskipun masih aktif. Hal ini dapat diterapkan sebagai sanksi kepada anggota yang melanggar peraturan perpustakaan.



1.3 Menu Member Type 

Merupakan definisi jenis keanggotaan. Di dalam jenis keanggotaan ini di tetapkan Loan Limit (batas eksemplar peminjaman), Loan Periode (lama pinjam), Reserve (pemesanan), Reserve Limit (batas eksemplar pemesanan), Membership Periode (lama keanggotaan), Reborrow Limit (batas perpanjangan), Fine Each Day (denda perhari), dan Overdue Grace Periode (Toleransi keterlambatan -dalam hari-). 



1.4 Menu Import Data 

Menu ini digunakan untuk mengambil data member dari luar aplikasi Senayan untuk dimasukkan ke dalam aplikasi Senayan. Format data yang di import adalah .csv. 

1.5 Menu Export Data 

Menu ini digunakan untuk mengambil data member didalam aplikasi senayan, dan hasilnya adakah data dalam bentuk .csv

Contoh record data csv dari member ini adalah: 

"M001","Hendro Wicaksono","0","Mahasiswa","hendrowicaksono@yahoo.com","Jakarta","99999","Perpustakaan DIKNAS","","member_M001.jpeg","KTP No. 123","99999","99999","2008-12-25","2008-12-25","2009-12-25","Anggota Teladan tahun 2006" 





1.6 Member Card

Menu ini digunakan untuk mencetak kartu anggota. Cara mencetaknya sama dengan cara mencetak label atau barcode. Informasi yang ada dalam kartu anggota ini adalah: ID, Nama, Member Type, Barcode, Foto (Jika ada) dan Identitas perpustakaan.



1.7 Member Custom Field

Serupa dengan Biblio Custom, pada fitur ini pengguna senayan dapat menambahkan informasi (field) baru yang harus diisikan dalam informasi keanggotaan. Untuk menambahkan field baru, langkah-langkahnya adalah sebagai berikut:

• Buka file member_custom_fields.inc.php yang terletak di folder /admin/modul/membership

• Dalam file ini terdapat 5 custom field yang dapat digunakan. Custom field ini dapat dihapus atau dikurangi. Misalnya akan di tambah 1 field baru untuk informasi status pernikahan. Maka custon 2-5 dihapus terlebih dahulu.

• Pada Custom Field 1 diisi sebagai berikut:

'dbfield' => 'status', // name of field in 'biblio' table in database, make sure you already define it! 

'label' => __('Status Pernikahan'), // label of field in form 

'type' => 'text', // type of field 

'default' => '', // default value of field 

'max' => '50', // maximum character to enter in 'text' field type

'data' => false, // an array of data for 'dropdown', 'checklist' or 'choice'

'indexed' => true, // NOT APPLICABLE YET, FOR FUTURE RELEASE USE

'width' => 50), // width of field in form for 'text' field type, maximum is 100

• Berikutnya adalah menambahkan field/kolom status pada tabel member.

• Hasil dari modifikasi ini adalah sebagai berikut (dapat dilihat pada add new member):

