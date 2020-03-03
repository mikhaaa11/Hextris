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
  1. Apache2
  2. PHP
  3. HTML5
  
# Konfigurasi
  - Dapat mengupload 
  - Dapat registrasi secara publik
  
# Otomatisasi

## Instalasi Web Server Virtual
1. Membuat VM Ubuntu Server
Membuat VM baru pada VirtualBox dengan tipe "Ubuntu 64-bit", menggunakan virtual disk Ubuntu Server 18.04.
![Membuat VM](Screenshot-1.png)
![Membuat VM2](Screenshot-2.png)



2. Setting Port-Forwarding VM
Tujuannya adalah agar VM bisa diakses dari luar melalui alamat IP host (localhost). Masuk ke 'Settings -> Network -> Advanced -> Port Forwarding' lalu ditambahkan dua aturan berikut.

  ![Port-Forwarding](Screenshot-3.png)

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
1. Lakukan cd ke var/www/html
2. Lakukan git clone <https://github.com/Hextris/hextris.git> 
3. Arahkan browser ke <http://localhost:8000/Hextris>

![Instalasi Hextris](Screenshot-8.png)
    
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
