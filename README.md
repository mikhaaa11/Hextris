![Calibre-web](https://raw.githubusercontent.com/husnarfh/calibre-web/master/calibre.PNG)

# Sekilas Tentang
Calibre-Web merupakan sebuah aplikasi berbasis web yang menyediakan interface untuk melakukan pencarian, membaca dan mengunduh ebooks menggunakan database Calibre yang sudah ada.


# Instalasi
  Requirements : 
  Untuk menginstall Calibre-Web membutuhkan beberapa hal, yaitu :
  1. Python 2.7+, python 3.x+
  2. requirements.txt yang berisi :
  - Babel>=1.3
  - Flask-Babel>=0.11.1
  - Flask-Login>=0.3.2
  - Flask-Principal>=0.3.2
  - singledispatch>=3.4.0.0
  - backports_abc>=0.4
  - Flask>=0.11
  - iso-639>=0.4.5
  - PyPDF2==1.26.0
  - pytz>=2016.10
  - requests>=2.11.1
  - SQLAlchemy>=1.1.0
  - tornado>=4.1
  - Wand>=0.4.4
  - unidecode>=0.04.19
  3. metadata.db (database) yang berasal dari aplikasi Calibre Library yang dapat didownload dan diinstall [disini](https://calibre-ebook.com/download)
  4. Amazon's KindleGen untuk fitur konversi buku
    
# Konfigurasi
  - Dapat mengupload 
  - Dapat registrasi secara publik
  
# Otomatisasi

## Instalasi Web Server Virtual
1. Membuat VM Ubuntu Server
Membuat VM baru pada VirtualBox dengan tipe "Ubuntu 64-bit", menggunakan virtual disk Ubuntu Server 18.04.
2. Setting Port-Forwarding VM
Tujuannya adalah agar VM bisa diakses dari luar melalui alamat IP host (localhost). Masuk ke 'Settings -> Network -> Advanced -> Port Forwarding' lalu ditambahkan dua aturan berikut.

  ![instalasi](pict/1.png)

3. Instalasi LAMP (Linux Apache MySQL PHP)
  ```bash
# akses vm dari host
ssh student@localhost -p 2222

# instal apache, mysql, php
sudo apt update
sudo apt upgrade
sudo apt install apache2 php mysql-server
sudo apt install php-mysql php-gd php-mbstring php-xml php-curl
sudo service apache2 restart
  ```
4. Karena requirement untuk menginstal calibre-web butuh Python 2.7+, python 3.x+, maka dilakukan instalasi
```bash
sudo apt-get install python
sudo apt-get install python3
```

## Instalasi Calibre-Web
1. Instal dependensi dengan menjalankan `pip install --target vendor -r requirements.txt.`
2. Jalankan perintah: `python cps.py` (atau `nohup python cps.py` - Direkomendasikan jika ingin menutup terminal windows)
3. Arahkan browser ke <http://localhost:8083> atau <http://localhost:8083/opds> untuk OPDS catalog
4. Atur `Location of Calibre database` ke folder penempatan Calibre library (metadata.db), tekan tombol “submit”
5. Masuk ke halaman Login
```bash
Default admin login:
Username: admin
Password: admin123
```

# Cara Pemakaian
- Tampilan aplikasi web:

![tampilan](pict/2.png)

- Fitur-fitur yang terdapat dalam calibre adalah sebagai berikut:
1. Library Management

  Calibre dapat mengurutkan buku berdasarkan: Judul, Penulis, Tanggal dimasukkan, Tanggal diterbitkan, Ukuran, Rating, Seri, dan lain-lain. Serta mendukung metode pencarian: tags, komentar dan advanced search. Selain itu, calibre dapat terhubung ke internet untuk menemukan buku berdasarkan judul, pengarang atau ISBN. Dan dapat mengunduh berbagai jenis metadata dan cover buku secara otomatis.
  
2. Mendownload berita dari web dan mengubahnya ke dalam bentuk e-book

  Calibre secara otomatis dapat mengambil berita dari website atau RSS feed, mengonversinya menjadi e-book dan mengunggahnya. E-book tersebut merupakan versi lengkap dari artikel, bukan hanya ringkasan.
  
3. Konversi e-book
  
  Calibre dapat mengonversi dalam berbagai format. Fitur dalam konversi e-book yaitu dapat mengatur ulang ukuran semua font, memastikan output e-book dapat dibaca, dan dapat mendeteksi atau membuat struktur buku.
  
Input Format: CBZ, CBR, CBC, CHM, EPUB, FB2, HTML, MENYALA, LRF, MOBI, ODT, PDF, RRC, PDB, PML, RB, RTF, SNB, TCR, TXT

Output Format: EPUB, FB2, OEB, MENYALA, LRF, MOBI, PDB, PML, RB, PDF, SNB, TCR, TXT

4. Memiliki server untuk mengakses koleksi e-book secara online
  
  Calibre mempunyai web server yang memungkinkan untuk mengakses koleksi e-book secara online. Calibre juga dapat mengirim e-book melalui e-mail dan mengunduh berita secara otomatis. Calibre juga mendukung perangkat mobile.

5. Sinkronisasi ke perangkat pembaca e-book
  
  Calibre memiliki driver perangkat desain modular yang menambah dukungan untuk perangkat e-reader yang berbeda. Proses sinkronisasinya yaitu calibre dapat memperbarui metadata koleksi berdasarkan tag yang didefinisikan di perpustakaan. Jika sebuah buku memiliki lebih dari satu format yang tersedia, calibre secara otomatis memilih format terbaik ketika mengunggah ke perangkat. Jika tidak ada format yang sesuai, secara otomatis calibre akan mengonversi e-book ke format yang sesuai untuk perangkat sebelum mengirimnya.

- Hasil screenshot website Calibre:
  - Tampilan login.
  
    ![login](pict/3.png)
    
  - Tampilan utama website.
  
    ![tampilan utama](pict/4.png)
  
  - Tampilan saat memilih buku.
  
    ![memilih buku](pict/5.png)
  
  - Tampilan saat mengedit informasi terkait buku.
  
    ![edit](pict/6.png)
  
  - Tampilan advanced search.
  
    ![search](pict/7.png)
  
  - Tampilan untuk mengupload.
  
    ![upload1](pict/8.png)
  
    ![upload2](pict/9.png)
    
# Pembahasan

- Kelebihan
  - Lebih praktis dan ringan
  - Dapat disimpan dalam jangka waktu yang lama dengan kemungkinan kerusakan yang minim
  - Distribusinya yang cepat dan mudah karena memanfaatkan jaringan internet
  - Cenderung lebih murah dibanding buku cetak
  
- Kekurangan
  - Bergantung dengan sumber daya listrik
  - Perangkat pembaca yang masih mahal
  - Terkait dengan masalah hak cipta
  
  *Aplikasi sejenis* : Google Play Books
  Banyak perbedaan antara Google Play Books dengan Calibre Web, yaitu :
  1. Masalah hak cipta
  2. Banyak fitur saat kegiatan membaca, misalnya mengubah warna background, menandai halaman, dan menyimpan kutipan.
  
 # Referensi
- <https://github.com/auriza>
- <https://github.com/janeczku/calibre-web>
- <https://calibre-ebook.com/>
- <https://syafruldzulfikarfajri.blogspot.com/2014/02/makalah-calibre.html>
- <https://donyprisma.wordpress.com/2012/07/05/calibre-e-book-management/>
