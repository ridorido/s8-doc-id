# Bab 6

1 Reporting

Librarians are subversive. You think they're just sitting there at the desk, all quiet and everything. They're like plotting the revolution. --Michael Moore

Reporting Modul ini berisi informasi laporan kegiatan perpustakaan. Informasi tersebut dapat diakses dengan menekan menu yang terdapat pada navigasi sebelah kiri. Menu tersebut: 

1.1 Collection Statistic

Berisi informasi total judul koleksi, total item, total item yang sedang dipinjam, total item yang berada di perpustakaan (tidak dipinjam), total judul berdasar GMD, total items berdasar tipe koleksi dan 10 (sepuluh) koleksi paling populer (paling banyak dipinjam). 



1.2 Loan Report 

Berisi informasi seputar peminjaman. Terdiri dari: total peminjaman, peminjaman berdasar GMD, peminjaman berdasar tipe koleksi, total transaksi peminjaman, rata-rata transaksi per hari, anggota yang sedang mempunyai pinjaman, anggota yang tidak mempunyai pinjaman, dan total peminjaman yang terlambat. 



1.3 Membership Report 

Berisi informasi keanggotaan, yaitu: total anggota yang terdaftar, total anggota aktif, total anggota berdasar tipe anggota, total anggota yang tidak aktif dan daftar 10 (sepuluh) anggota teraktif. 



Laporan yang ada dalam tiga menu tersebut dapat diperoleh dalam format .html dan dapat dicetak dengan klik tombol Download Report

Mulai Senayan3-stable14, ketiga jenis laporan ini dilengkapi dengan fitur cetak grafik berjenis Pie. Untuk mendapatkan Grafik ini cukup dengan klik Show in Chart/Plot yang muncul pada ketiga jenis laporan ini (Collection Statistic, Loan Report dan Membership Report).





1.4 Customs Reccapitulations

Menu ini menampilkan hasil rekapitulasi koleksi berdasar Classification, GMD, Colection Type atau Language. Pilihan ini dapat kita tentukan dengan memilih filter rekapitulasi yang tersedia. Senayan juga telah mendukung rekap untuk klasifikasi yang bukan didasarkan pada angka desimal. Misalnya REF untuk referensi. 



Pada modul Report di Senayan3-Stable10 ini, ada pengembangan untuk memudahkan pengguna senayan dalam membuat sebuah modul laporan baru.

Pada folder /senayan3-stable10/admin/modules/reporting/custom/ terdapat file customs_report_list.inc.php. Pada file inilah modifikasi dan penambahan report bisa dilakukan.

1.5 Titles

Berisi laporan/daftar judul yang dimikili oleh perpustakaan. Dalam menu ini terdapat fasilitas untuk mengurutkan dan mencetak, serta memfilter koleksi yang diinginkan. Pada menu ini, dapat pula dilakukan filtering dengan menuliskan Title/ISBN, atau dengan menampilkan fasilitas filter lainnya. Caranya dengan klik Show More Filter Options. Fasilitas filter yang ada adalah: Title/ISBN, Author, Classification, GMD, Langage dan Location, serta dapat ditentukan jumlah tampilan tiap halaman.



1.6 Items title List 

Berisi laporan/daftar item yang dimikili oleh perpustakaan. Dalam menu ini terdapat fasilitas untuk mengurutkan dan mencetak. Pada menu ini, dapat pula dilakukan filtering dengan menuliskan Title/ISBN, atau dengan menampilkan fasilitas filter lainnya. Caranya dengan klik Show More Filter Options. Fasilitas filter yang tersedia adalah: Title/ISBN, Item Code, Classification, Collection Type, Item Status, Location. Fasilitas filter ini dapat di sembunyikan dengan klik Hide Filter Option



1.7 Item Usage

Merupakan laporan yang menginformasikan item, title dan berapakali item tersebut dipinjam pada setiap bulannya. Item usage ini dapat pula difilter dengan Title/ISBN, Item code atau Year.



1.8 Loan by Classification

Merupakan laporan peminjaman berdasar Klasifikasi. Selain kelas 0-9, pada laporan ini juga dimungkinkan pelaporan berdasarkan kelas 2X dan Non Decimal Class. Loan by Class ini dapat difilter dengan Class, Colection Type dan Year.



1.9 Member List 

Berisi laporan/daftar anggota perpustakaan. Dalam menu ini terdapat fasilitas untuk mengurutkan dan mencetak. Selain itu, terdapat pula fasilitas filter, yaitu: berdasar Membership Type, Member ID/Member Name, Gender, Address, Register Date From, Register Date Until.



1.10 Loan List by Member

Merupakan laporan yang berisi daftar koleksi yang masih di pinjam Anggota.



1.11 Loan History 

Berisi laporan/daftar sejarah peminjaman perpustakaan. Dalam menu ini terdapat fasilitas untuk mengurutkan dan mencetak. Pada menu ini, dapat pula dilakukan filtering dengan menuliskan Member ID/Member Name, atau dengan menampilkan fasilitas filter lainnya. Caranya dengan klik Show More Filter Options



1.12 Overdued List 

Berisi laporan/daftar keterlambatan pengembalian anggota perpustakaan. Dalam menu ini terdapat fasilitas untuk mengurutkan dan mencetak. 



1.13 Staff Activity

Menu ini memperlihatkan aktifitas Staff perpustakaan yang mempunyai account di aplikasi Senayan. Informasi yang ditampilkan adalah Username, Login Name, Bibliografy data entry, Item data Entry, Member data entry, dan Circulation. Jadi dengan menu ini akan terlihat staff melakukan apa dan berapa kali.

Untuk memperakurat informasi, disediakan pula filter yang memungkinkan kita melihat aktifitas dari tanggal awal sampai akhir (seperti yang ditentukan).



1.14 Visitor Statistic

Merupakan laporan yang berisi statistik pengunjung perpustakaan --yang melakukan pendataan pada saat masuk perpustakaan melalui fasilitas absensi--. Laporan ini berisi Member Type, dan jumlah kunjungan pada tiap bulan pada tahun yang ditentukan. Penentuan laporan berdasar tahun ini dapat dilakukan melalui Filter.



1.15 Visitor Statictic by day

Merupakan laporan jumlah pengunjung berdasarkan hari. 



1.16 Visitor List

Laporan ini berisi daftar nama anggota atau non anggota perpustakaan yang berkunjung ke perpustakaan. Informasi pada laporan ini berisi Member ID, Member Name, Member Type, Institution dan Visit date.



Penjelasan mengenai fitur absen, silakan lihat pada bagian Absen.

1.17 Fines Report

Merupakan laporan jumlah denda anggota perpustakaan berdasar hari. 



1.18 Due date Warning

Fitur ini berisi informasi peminjam koleksi perpustakaan yang dalam 3 hari ini akan tepat pada batas peminjaman.

