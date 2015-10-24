# Bab 5

1 Stoke Take

I have always imagined that Paradise will be a kind of library. --Jorge Luis Borges

Modul Stock Take merupakan fasilitas yang ada di Senayan untuk membantu para pustakawan melakukan kegiatan stock opname. Ketika proses stock opname dimulai, semua koleksi kecuali yang sedang dipinjam (berstatus on loan) akan dianggap hilang, lalu masuk ke dalam menu current lost item sampai koleksi yang bersangkutan di cek pada proses stock take. Menu-menu yang terdapat pada modul ini adalah: 

1.1 Menu Stock Take History 

Berisi laporan stock opname yang telah dilakukan. Informasi dalam menu ini adalah: Stock Take Name, Start Date, end Date, Report. Report berisi link ke dokumen berbentuk .html yang berisi laporan Stock take yang pernah dilakukan. 



1.2 Menu Initialize 

Menu Initialize digunakan untuk memulai stock opname. Pada menu ini, terdapat sub-sub menu: 

• Stock Take Name Adalah nama dari kegiatan stock opname yang dilakukan. Sesuaikan namanya dengan keinginan Anda. Sub menu ini HARUS diisi. 

• GMD (Lihat panduan modul Master File --> GMD (di bawah Authority Files)). 

• Collection Type (Lihat panduan modul Master File --> Collection Type (di bawah Lookup Files)). 

• Location (Lihat panduan modul Master File --> Location (di bawah Authority Files)). 

• Site/Placement Mengacu ke informasi item pada modul Bibliography. 

• Classification Mengacu ke sub menu class pada modul Bibliography. Untuk penulisan class menggunakan wildcard (*), misal, apabila kita ingin melakukan stock opname dengan kisaran class 100 s.d.300, cukup masukkan 1* to 3*. Apabila kisaran class yang kita lakukan stock opname hanya pada class 100, masukkan 1*. 





Setalah proses Initialize dilakukan, maka menu current stoke take dan stock take report akan berfungsi sebagai menu untuk melakukan kegiatan stock take ditambah dengan adanya menu menu tambahan yang akan digunakan untuk melakukan kegiatan stock take, yaitu menu Finish Stock Take, Current Lost Items, Stock Take Log, Resyncronize. (Lihat gambar) 

1.3 Menu Current Stock Take 

Menu itu adalah menu utama untuk melakukan stock take. Menu ini digunakan untuk mengembalikan status koleksi perpustakaan yang dianggap hilang oleh sistem, ke status exist (koleksi dinyatakan ada). Pada menu ini, item id (nomor barcode) koleksi menjadi acuan utama untuk mengubah status koleksi yang dianggap hilang menjadi exist (ada), Caranya dengan memasukan nomor barcode koleksi tersebut pada kolom Item Code. Menu ini akan berfungsi apabila telah dilakukan proses Initialize. 

Pada stable11, terdapat fitur List stocktakes by: yang dapat dipilih Current User Only, yang berarti daftar item yang terlihat adalah yang distocktake oleh user yang bersangkutan. Atau All User, berarti daftar item yang distocktake adalah item yang distocktake oleh semua user yang melakukan stocktake.



1.4 Menu Stock Take Report 

Menu ini untuk melihat hasil dari kegiatan stocke take yang telah dilakukan. Bentuknya berupa laporan (report) yang memuat informasi tentang jumlah koleksi yang hilang, yang sedang dipinjam dan sebaginya. Menu ini tidak berfungsi apabila proses Initialize belum dilakukan.



1.5 Finish Stock Take 

Klik link ini apabila kita telah selesai melakukan stock opname. Didalam menu ini, terdapat sub menu Purge Lost Item. Apabila kita memberikan tanda cek pada Yes, maka data item pada bibliography yang berada dalam Current Lost Item akan ditandai dengan “Missing”.



1.6 Current Lost Items 

Isi menu ini merupakan daftar dari koleksi yang dianggap hilang pada saat stock opname selain koleksi yang dipinjam.



1.7 Stock take Log 

Fungsi menu ini adalah untuk mengetahui rekaman (Log) saat melakukan proses stock take 



1.8 Resyncronize 

Menu ini digunakan untuk melakukan sinkronisasi data bibliografi yang diedit pada saat berlangsung kegiatan stock take dengan data bibliografi yang ada pada modul stock take. Tujuannya adalah ketika kita melakukan editing data bibliografi saat dilakukannya proses stock take, maka untuk menghasilkan perubahan pada data bibliografi yang terdapat di modul stock take, perlu dilakukan resinkronisasi data. Klik tombol Resyncronize begitu perubahan data bibliografi sudah dilakukan.



1.9 Upload List

Menu ini digunakan untuk melakukan stock take otomatis dengan memanfaatkan file data item. Untuk dapat menggunakan Upload List, pertama data item senayan harus dieksport, kemudian khusus item disimpan dalam file .txt secara berbaris.



