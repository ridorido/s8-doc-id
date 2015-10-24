# Bab 4

1 Circulation

What in the world would we do without our libraries? --Katherine Hepburn

Modul ini dipakai untuk proses sirkulasi. Beberapa menu yang ada di dalamnya adalah: 

1.1 Menu Start Transaction 

Untuk melakukan transaksi melalui Member ID (ID anggota). Setelah Member ID dimasukkan, maka akan muncul informasi anggota, yaitu: Member Name (nama anggota), Member E-Mail (email anggota), Register Date (tanggal mendaftar), Member ID (ID anggota), Member Type (jenis keanggotaan), Expire Date (tanggal akhir keanggotaan) dan foto anggota. Dibawahnya terdapat tab Loans (untuk melakukan transaksi peminjaman), Current Loans (daftar peminjaman terkini), Reserve (untuk kebutuhan pemesanan literatur), Fines (denda), Loan History (sejarah peminjaman yang dilakukan oleh anggota). Dalam Current Loans juga terdapat fasilitas untuk mengembalikan (Return) dan memperpanjang (Extend) peminjaman. 



Catatan: 

Setelah selesai melakukan proses peminjaman (Loans) dan Pemesanan (Reserve) jangan lupa untuk klik Finish Transaction. Tanpa menekan tombol Finish Transaction, maka semua proses transaksi tidak akan tercatat ke dalam sistem. 

Mulai pada Senayan3-stable13 tersedia fitur cetak nota transaksi. Untuk mengaktifkan fitur ini, pertama harus diseting enable pada modul System. Lihat dokumentasi bagian System. Perintah mencetak akan muncul setelah pustakawan meng-klik Finish Transaction.



Mulai Senayan3-stable11, dimungkinkan untuk menentukan tanggalpinjam dan kembali secara manual. Artinya, tanggal pinjam dan kembali dapat ditentukan dengan tidak berdasar konfigurasi pada Loan Rules. Untuk aktivasi silakan lihat pada Modul System Configurations.



Penentuan Loan dan Due date ini dapat dilakukan dengan meng-klik tanggal yang ingin kita ubah. 

1.2 Menu Quick Return 

Untuk melakukan pengembalian dengan menggunakan Item Id. 



1.3 Menu Loan Rules 

Merupakan fasilitas untuk mendefinisikan aturan peminjaman yang didasarkan pada Member Type, Collection Type, GMD. Aturan yang ditetapkan dalam fasilitas ini adalah Batas Jumlah Peminjaman (Loan Limit), Periode Peminjaman (Loan Period), Batas Perpanjangan (Reborrow Limit), Denda per Hari (Fine Each Day) dan Toleransi Keterlambatan (Overdue Grace Periode) 



ContohPendefinisian Loan Rules: 

1. diperpustakaan anda ada 3 tipe koleksi: Buku, AudioVisual (AV), Skripsi. 

2. Salah satu tipe keanggotaan di perpustakaan anda adalah: Mahasiswa dengan jatah pinjam total 2 koleksi, yaitu: 1 untuk tipe koleksi Buku dan 1 lagi untuk tipe koleksi AV. 

3. Untuk itu tentu anda harus membuat tipe membership "Mahasiswa" dengan total peminjaman dua koleksi. 

4. Kemudian di loan rulesnya yang harus didefinisikan:

• jenis member "Mahasiswa" jatah pinjem koleksi "Buku" adalah 1.

• jenis member "Mahasiswa" jatah pinjem koleksi "AV" adalah 1. 

• jenis member "Mahasiswa" jatah pinjem koleksi "Skripsi" adalah 0.

Semuanya harus didefinisikan, jika tidak maka bisa jadi terlewati. 

1.4 Menu Loan History 

Berisi data transaksi yang pernah dilakukan. Data yang muncul terdiri dari Member ID, Member Name, Item Code, Title, Loan date, Due date. Dalam menu ini pula disediakan fasilitas untuk mencetak daftar history peminjaman. Selain itu dimungkinkan pula untuk melakukan pencarian data history. Pencarian data history ini dilakukan berdasarkan Member ID/Member Name, Documen Title, Item Code, Loan Date From dan Loan Date Until. Fasilitas ini dapat di tampilkan dengan mengklik Show More Filter Options. 



1.5 Menu Overdued List 

Merupakan fasilitas untuk mengetahui anggota-anggota dengan status terlambat. Informasi yang ditampilkan dalam fasilitas ini adalah Member ID, Member Name, Title, lama keterlambatan, Loan Date, Due Date. Dengan Menu ini pula kita dapat melakukan pencetakan dan pencarian data keterlambatan. Pencarian data keterlambatan dilakukan berdasarkan kategori Member ID/Member Name, Loan Date From, Loan Date Until. 



1.6 Menu Reserve

Menu ini digunakan untuk melihat daftar koleksi yang sedang di pesan oleh anggota. informasi yang ada dalam menu ini adalah: Item Code, Title, Member, Reserve Date

