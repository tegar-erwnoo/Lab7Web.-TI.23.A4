|Nama|NIM|Kelas|Matkul|
|----|---|-----|------|
|M Tegar Hermawanto|312310404|TI.23.A4|Pemograman Web 2|

Praktikum 1: PHP Framework (Codeigniter)

Langkah-langkah Praktikum
Persiapan
Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada
webserver. Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan
Codeigniter 4.
Berikut beberapa ekstensi yang perlu diaktifkan:
• php-json ekstension untuk bekerja dengan JSON;
• php-mysqlnd native driver untuk MySQL;
• php-xml ekstension untuk bekerja dengan XML;
• php-intl ekstensi untuk membuat aplikasi multibahasa;
• libcurl (opsional), jika ingin pakai Curl.
Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache
klik Config -> PHP.ini

![image](https://github.com/user-attachments/assets/9ae8d3c2-2648-41a8-bbc5-bf14fd6effde)

Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan.
Kemudian simpan kembali filenya dan restart Apache web server.

![image](https://github.com/user-attachments/assets/36dc4618-8d03-461b-80de-7050cad95395)

Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual
dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.
• Unduh Codeigniter dari website https://codeigniter.com/download
• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
• Ubah nama direktory framework-4.x.xx menjadi ci4.
• Buka browser dengan alamat http://localhost/lab11_ci/ci4

![image](https://github.com/user-attachments/assets/13abc973-5274-4d1f-9ff4-6c4c7d561d28)

Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses
CLI buka terminal/command prompt.

![image](https://github.com/user-attachments/assets/164d6021-effc-431e-bc48-79b0b2165186)

Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat
(xampp/htdocs/lab11_ci/ci4)

Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:
php spark serve

![image](https://github.com/user-attachments/assets/3031d1e7-7440-480d-9fa7-3ba90b440cd8)

Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui
pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan
kesalahan seperti berikut.

![image](https://github.com/user-attachments/assets/d6b261ec-5f9e-4fc1-866c-44bf819b1223)

Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada
codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css
dan javascript terletak pada direktori public.
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum
lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![image](https://github.com/user-attachments/assets/09be9b97-3951-4dca-b0b9-78de72588b17)

PRAKTIKUM 2 : FRAMEWORK LAJUTAN (CRUD)

![image](https://github.com/user-attachments/assets/cb358013-6a74-4c7a-b42d-6a9e419c0b87)
Konfigurasi koneksi database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi
dapat dilakukan dengan du acara, yaitu pada file app/config/database.php atau menggunakan
file .env. Pada praktikum ini kita gunakan konfigurasi pada file .env.

![image](https://github.com/user-attachments/assets/f2084c6c-a923-45e6-ae5c-49e62070cbaf)

Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada
direktori app/Models dengan nama ArtikelModel.php

![image](https://github.com/user-attachments/assets/77f62723-9455-4bb9-97d1-2f70b83f9944)

Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada
direktori app/Models dengan nama ArtikelModel.php

![image](https://github.com/user-attachments/assets/cf53de8b-e05b-4bbd-8419-3a0bb3f9cd71)

Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru
dengan nama index.php.

![image](https://github.com/user-attachments/assets/05e4640a-648f-49e2-a28d-79ff2cbf373b)

![image](https://github.com/user-attachments/assets/3bd55b5a-d1df-4c29-a471-bf06543d9ff7)





































