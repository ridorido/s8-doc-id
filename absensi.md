# Bab 11

1 Modul Absensi (Penghitungan Pengunjung)

Modul ini dapat dipanggil melalui:

http://localhost/senayan3-stable14/?p=visitor

Tampilan modul ini adalah sebagai berikut:



Pengunjung perpustakaan dibedakan menjadi 2; Anggota yang sudah terdaftar dan pengunjung yang bukan anggota/tidak terdaftar.

Jika sudah terdaftar, maka pengunjung cukup menuliskan Member ID pada kolom atas, kemudian tekan Enter atau klik Add. Maka data sudah tersimpan 1 x kunjungan lengkap dengan jam dan tanggal kunjung. Namun jika bukan anggota terdaftar, maka harus secara manual menuliskan Nama dan Institusi (wajib).

Untuk keamanan dan validitas proses absensi pengunjung, Visitor Counter ini dapat di seting hanya komputer dengan Internet Protokol tertentu saja yang dapat mengakses. Pengaturan ini terdapat dalam file visitor.inc.php yang ada dalam folder /senayan/lib/contents/visitor.inc.php. Scriptnya adalah sebagai berikut:

$allowed_counter_ip = array('127.0.0.1');

Pada script diatas, 127.0.0.1 merupakan IP address yang diijinkan untuk mengakses visitor counter. Jika ada lebih dari satu komputer maka IP Address komputer yang bersangkutan harus diisikan didalam script diatas. Misalnya, komputer dengan IP 10.45.1.1, 10.45.1.2 dan 10.45.1.3, maka penulisannya adalah:

$allowed_counter_ip = array('10.45.1.1', '10.45.1.2','10.45.1.3');

Laporan kunjungan ini dapat dilihat pada modul reporting. Namun demikian akses ke IP Server akan terganggu jika broser anda menggunakan proxy. Oleh karena itu, anda dapat menghapus seting proxy menuju server SLiMS anda. 