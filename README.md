![Hextris](Hextris.jpg)

# Sekilas Tentang
Hextris merupakan sebuah permainan berbasis web yang memiliki konsep seperti tetris, hanya saja dengan enam sisi yang harus diisi. Bila pemain dapat menyusun 3 atau lebih blok secara horizontal atau vertikal maka blok tersebut akan menghilang dan pemain mendapatkan poin, permainan berakhir apabila salah satu dari keenam sisi terisi penuh.

# Control
| Tombol Keyboard | Fungsi |
| ----- | ----- |
| Arrow Left atau A | Memutar Hexagon ke kiri |
| Arrow Right atau D | Memutar Hexagon ke kanan |
| Arrow Down atau S | Mempercepat blok turun |


# Instalasi
  Requirements : 
  Untuk menginstall Hextris membutuhkan beberapa hal, yaitu :
  1. HTML5
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
ssh student@localhost -p 2200

# set repo
sudo tee /etc/apt/sources.list << !
deb http://repo.apps.cs.ipb.ac.id/ubuntu bionic          main restricted universe multiverse
deb http://repo.apps.cs.ipb.ac.id/ubuntu bionic-updates  main restricted universe multiverse
deb http://repo.apps.cs.ipb.ac.id/ubuntu bionic-security main restricted universe multiverse
!

# instal apache, mysql, php
sudo apt update
sudo apt upgrade
sudo apt install apache2 php mysql-server
sudo apt install php-mysql php-gd php-mbstring php-xml php-curl
sudo service apache2 restart
  ```


## Instalasi Hextris
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
- <https://github.com/Hextris/hextris>

# Sitasi
```bash
@misc{engstrom2015hextris,
    author = {Logan Engstrom, Garrett Finucane, Noah Moroze, Michael Yang},
    title = {hextris},
    year = {2015},
    howpublished = {\url{https://github.com/hextris/hextris/}},
    note = {commit xxxxxxx}
  }
```
