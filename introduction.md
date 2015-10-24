
# 

#Dokumentasi SLiMS Berdasar SLiMS-8 
ditulis dengan [Gitbook Editor](https://www.gitbook.com/editor)


Menggunakan piranti lunak free open source/free software itu ibarat kita mengutip pernyataan dari karya orang lain dalam bidang akademik, si penulis asli ga minta apa-apa kok, minta duit juga engga, cuman minta nama dan karya dia disebutin dengan baik dan benar, udah segitu doang engga susah kan? (Arie Nugraha, Core Programmer SLiMS)

Update di SLiMS-8 (AKASIA):

• Add: Template admin untuk Cendana 

• Add: OPAC Responsive template



Catatan Penting:

Sysconfig

File sysconfig.local.inc.php, merupakan file yang berfungsi sama konfigurasi sama dengan sysconfig.inc.php. Namun demikian, untuk perubahan di lokal, disarankan mengubah file sysconfig.local.inc.php saja. Logikanya, jika ada dua konfigurasi sama di kedua file tersebut, maka yang akan dibaca oleh aplikasi SLiMS adalah sysconfig.local.inc.php.

Misal:

Pada sysconfig.inc.php ada baris $sysconf['ucs']['enable'] = false;

Pada sysconfig.local.inc.php ada baris $sysconf['ucs']['enable'] = true;

Maka yang akan digunakan oleh Aplikasi SLiMS adalah konfigurasi yang bernilai true.

Shortcut

Mulai SLiMS-5, SLiMS mempunyai fitur shortcut yang dapat digunakan untuk berpindah menu tanpa menggunakan mouse. Shortcut tersebut berlaku untuk MODUL dan SUBMODUL. Modul menggunakan perpaduan Shift+Tombol Fungsi (F1-F8 dan Esc), sedangkan Submodul menggunakan perpaduan Ctrl+Angka 1-8, pada bagian yang mempunyai submodul banyak ada yang juga menggunakan perpaduan Ctrl+Alt+Angka.


Selain itu, juga ada shortcut untuk menu di submodul sirkulasi. Yaitu (L), (C), (R),(F),(H). Cara mengaksesnya adalah dengan Alt+Shift+(L) dan seterusnya (jika anda menggunakan Firefox). Untuk browser lain, jika cara tersebut tidak berhasil dapat dengan menekan Alt+(L) dan seterusnya (tanpa shift).



Browser

Rekomendasi browser/perambah web untuk SLiMS adalah:

1. Firefox 10 ke atas

2. Chrome 10 ke atas

3. IE 9 ke atas

4. Opera 10 ke atas
