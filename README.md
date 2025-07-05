|Nama|NIM|Kelas|Matkul|
|----|---|-----|------|
|M Tegar Hermawanto|312310404|TI.23.A4|Pemograman Web 2|

Praktikum 1: PHP Framework (Codeigniter)

Langkah-langkah Praktikum
Persiapan
1. Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada
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

2. Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan.
Kemudian simpan kembali filenya dan restart Apache web server.

![image](https://github.com/user-attachments/assets/36dc4618-8d03-461b-80de-7050cad95395)

3. Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual
dan menggunakan composer. Pada praktikum ini kita menggunakan cara manual.
• Unduh Codeigniter dari website https://codeigniter.com/download
• Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
• Ubah nama direktory framework-4.x.xx menjadi ci4.
• Buka browser dengan alamat http://localhost/lab11_ci/ci4

![image](https://github.com/user-attachments/assets/13abc973-5274-4d1f-9ff4-6c4c7d561d28)

4. Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses
CLI buka terminal/command prompt.

![image](https://github.com/user-attachments/assets/164d6021-effc-431e-bc48-79b0b2165186)

5. Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat
(xampp/htdocs/lab11_ci/ci4)

Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah:
php spark serve

![image](https://github.com/user-attachments/assets/3031d1e7-7440-480d-9fa7-3ba90b440cd8)

6. Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui
pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan
kesalahan seperti berikut.

![image](https://github.com/user-attachments/assets/b5e6e606-9b78-424b-8cf1-edb1b6f72e0f)

7. Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya,
maka perlu diaktifkan mode debugging dengan mengubah nilai konfigurasi pada environment
variable CI_ENVIRINMENT menjadi development.

![image](https://github.com/user-attachments/assets/4ae40147-e188-46e9-b14b-ffd0e33eed01)

Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
CI_ENVIRINMENT menjadi development.

![image](https://github.com/user-attachments/assets/457e7a6a-474d-4f59-8208-f1bc1cdb33be)

Contoh error yang terjadi. Untuk mencoba error tersebut, ubah kode pada file
app/Controller/Home.php hilangkan titik koma pada akhir kode.

![image](https://github.com/user-attachments/assets/ed11d490-dc4f-431f-8d8e-ce1fd94dce35)

8. Pada Codeigniter, request yang diterima oleh file index.php akan diarahkan ke Router untuk
meudian oleh router tesebut diarahkan ke Controller.
Router terletak pada file **app/config/Routes.php**

![image](https://github.com/user-attachments/assets/d4492232-bce8-43f8-a232-fce17fdce80f)

9. Membuat Route Baru.
Tambahkan kode berikut di dalam **Routes.php**

$routes->get('/about', 'Page::about');
$routes->get('/contact', 'Page::contact');
$routes->get('/faqs', 'Page::faqs');

![image](https://github.com/user-attachments/assets/e0df964a-7992-4fa7-964f-61993655aab0)

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah
berikut.

![image](https://github.com/user-attachments/assets/5c07fc9e-65dc-46af-8891-10742ae7581d)

Selanjutnya coba akses route yang telah dibuat dengan mengakses alamat url
http://localhost:8080/about

![Screenshot 2025-03-21 131531](https://github.com/user-attachments/assets/2f3edd4f-6569-43a8-9800-b6273c99b5bc)

Ketika diakses akan mucul tampilan error 404 file not found, itu artinya file/page tersebut tidak
ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu Contoller yang
sesuai dengan routing yang dibuat yaitu Contoller Page.

10. Membuat Controller
Selanjutnya adalah membuat Controller Page. Buat file baru dengan nama **page.php** pada
direktori Controller kemudian isi kodenya seperti berikut.

![image](https://github.com/user-attachments/assets/c299574b-ce23-460a-a56d-3db282e82ac3)

Selanjutnya refresh Kembali browser, maka akan ditampilkan hasilnya yaotu halaman sudah
dapat diakses.

![Screenshot 2025-03-21 132900](https://github.com/user-attachments/assets/3f5987fd-8fe8-4cf8-8a19-e067cc3fef12)

11. Auto Routing
Secara default fitur autoroute pada Codeiginiter sudah aktif. Untuk mengubah status autoroute
dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai true menjadi false.

Method ini belum ada pada routing, sehingga cara mengaksesnya dengan menggunakan
alamat: http://localhost:8080/page/tos

![image](https://github.com/user-attachments/assets/31cf84ba-697f-443b-87e3-dd2789cc8637)

12. Membuat View
Selanjutnya dalam membuat view untuk tampilan web agar lebih menarik. Buat file baru
dengan nama **about.php** pada direktori view **(app/view/about.php)** kemudian isi kodenya
seperti berikut.

![image](https://github.com/user-attachments/assets/daff301b-6d8d-4be0-a055-325edffa0e96)

Ubah method about pada class Controller Page menjadi seperti berikut:

<img width="627" alt="image" src="https://github.com/user-attachments/assets/9d95d4ac-d564-4f7e-a5a0-3434f6ea8e52" />

Kemudian lakukan refresh pada halaman tersebut.

![image](https://github.com/user-attachments/assets/b285993b-bf83-449c-a4d4-e283d25cb86c)

13. Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan css dapat diimplamentasikan dengan mudah pada
codeigniter. Yang perlu diketahui adalah, pada Codeigniter 4 file yang menyimpan asset css
dan javascript terletak pada direktori public.
Buat file css pada direktori public dengan nama style.css (copy file dari praktikum
lab4_layout. Kita akan gunakan layout yang pernah dibuat pada praktikum 4.

![image](https://github.com/user-attachments/assets/d4099607-3343-4ae5-b1e7-c972aed2c39b)

Kemudian buat folder template pada direktori view kemudian buat file **header.php**h dan
**footer.php**

![image](https://github.com/user-attachments/assets/3fb3cbc9-7f2f-4e8f-bbec-7a1abcc84c65)

File **app/view/template/footer.php**

![Screenshot 2025-03-21 134623](https://github.com/user-attachments/assets/ec607eeb-4662-459a-b9cb-64b2fe96b717)

Kemudian ubah file **app/view/about.php** seperti berikut.

![image](https://github.com/user-attachments/assets/cd5c4862-8a4b-4fab-a187-83a853bfbc5b)

Selanjutnya refresh tampilan pada alamat http://localhost:8080/about

![image](https://github.com/user-attachments/assets/09be9b97-3951-4dca-b0b9-78de72588b17)

PRAKTIKUM 2 : FRAMEWORK LAJUTAN (CRUD)

14. Membuat database di my sql dengan nama lab_ci4

![image](https://github.com/user-attachments/assets/cb358013-6a74-4c7a-b42d-6a9e419c0b87)

15.  Konfigurasi koneksi database
Selanjutnya membuat konfigurasi untuk menghubungkan dengan database server. Konfigurasi
dapat dilakukan dengan du acara, yaitu pada file **app/config/database.php** atau menggunakan
file **.env.** Pada praktikum ini kita gunakan konfigurasi pada file **.env.**

![image](https://github.com/user-attachments/assets/f2084c6c-a923-45e6-ae5c-49e62070cbaf)

16. Membuat Model
Selanjutnya adalah membuat Model untuk memproses data Artikel. Buat file baru pada
direktori app/Models dengan nama ArtikelModel.php

![image](https://github.com/user-attachments/assets/77f62723-9455-4bb9-97d1-2f70b83f9944)

17. Membuat Controller
Buat Controller baru dengan nama **Artikel.php** pada direktori app/Controllers.

![image](https://github.com/user-attachments/assets/898d6d00-d37a-4437-b348-2320f0c9e88c)

18. Membuat View
Buat direktori baru dengan nama artikel pada direktori app/views, kemudian buat file baru
dengan nama **index.php.**

![image](https://github.com/user-attachments/assets/daac512a-cc9f-4006-9f8a-d8381b91b38e)

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel

![image](https://github.com/user-attachments/assets/2095cbd0-8697-4dce-8fa2-9ec28b9d4663)

Belum ada data yang diampilkan. Kemudian coba tambahkan beberapa data pada database agar
dapat ditampilkan datanya.

**INSERT INTO artikel (judul, isi, slug) VALUE
('Artikel pertama', 'Lorem Ipsum adalah contoh teks atau dummy dalam industri percetakan dan penataan huruf atau typesetting. Lorem Ipsum telah
menjadi standar contoh teks sejak tahun 1500an, saat seorang tukang cetak
yang tidak dikenal mengambil sebuah kumpulan teks dan mengacaknya untuk
menjadi sebuah buku contoh huruf.', 'artikel-pertama'),
('Artikel kedua', 'Tidak seperti anggapan banyak orang, Lorem Ipsum
bukanlah teks-teks yang diacak. Ia berakar dari sebuah naskah sastra latin
klasik dari era 45 sebelum masehi, hingga bisa dipastikan usianya telah
mencapai lebih dari 2000 tahun.', 'artikel-kedua');**

Refresh kembali browser, sehingga akan ditampilkan hasilnya.

![image](https://github.com/user-attachments/assets/3bd55b5a-d1df-4c29-a471-bf06543d9ff7)

19. Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda.
Tambahkan fungsi baru pada Controller Artikel dengan nama **view**().

![image](https://github.com/user-attachments/assets/694b677e-32b6-485e-bf99-531bbeda5ae1)

20. Membuat View Detail
Buat view baru untuk halaman detail dengan nama app/views/artikel/detail.php.

![image](https://github.com/user-attachments/assets/bc4c446e-1422-4bc3-a27a-68247fed4031)

21. Membuat Routing untuk artikel detail
Buka Kembali file **app/config/Routes.php**, kemudian tambahkan routing untuk artikel detail.

![image](https://github.com/user-attachments/assets/96a83682-0286-4a77-ab61-74fd887711eb)

![image](https://github.com/user-attachments/assets/960ded60-038f-4163-917b-e92d9c3c165a)

22. Membuat Menu Admin
Menu admin adalah untuk proses CRUD data artikel. Buat method baru pada Controller
Artikel dengan nama admin_index().

![image](https://github.com/user-attachments/assets/ddf0aa58-10bd-4a2a-afc3-a5cb00e770e5)

Selanjutnya buat view untuk tampilan admin dengan nama **admin_index.php**

![Screenshot 2025-03-23 135513](https://github.com/user-attachments/assets/7a5e3ccf-89eb-4699-88a3-36317d84c097)

![Screenshot 2025-03-23 135534](https://github.com/user-attachments/assets/1a872862-e42b-4843-a3c1-443e099ffd8d)

![Screenshot 2025-03-23 135750](https://github.com/user-attachments/assets/bd54a369-8ce0-4851-bdc2-5d679efaf666)

![Screenshot 2025-03-23 135806](https://github.com/user-attachments/assets/4af20293-7339-4195-8d14-06a92594ddc6)

Tambahkan routing untuk menu admin seperti berikut:

![image](https://github.com/user-attachments/assets/03d240eb-467b-4508-a385-7051320b167f)

Akses menu admin dengan url http://localhost:8080/admin/artikel

![Screenshot 2025-03-23 140106](https://github.com/user-attachments/assets/a29dda68-4955-46d5-952d-79e928701737)

23. Menambah Data Artikel
Tambahkan fungsi/method baru pada Controller Artikel dengan nama add().

![image](https://github.com/user-attachments/assets/021a3384-b68b-4b3a-b8ac-4c670e476005)

Kemudian buat view untuk form tambah dengan nama **form_add.php**

![Screenshot 2025-03-23 140417](https://github.com/user-attachments/assets/60aa76cb-c0f2-4b26-a3b3-2728e6ca4a77)

![image](https://github.com/user-attachments/assets/c4523463-46d7-4213-af73-b958cd279108)

24. Mengubah Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama **edit().**

![image](https://github.com/user-attachments/assets/d8684394-4097-4550-be78-cdb8857ad6bb)

Kemudian buat view untuk form tambah dengan nama **form_edit.php**

![image](https://github.com/user-attachments/assets/e576d3f0-5785-4f69-9129-1945e790ad72)

![image](https://github.com/user-attachments/assets/300bb226-325c-4de1-9481-aa998e38b4c7)

25. Menghapus Data
Tambahkan fungsi/method baru pada Controller Artikel dengan nama **delete()**.

![image](https://github.com/user-attachments/assets/276a3ee5-2b3a-4470-8a1d-a662d94fcb91)

PRAKTIKUM 3 : View Layout dan View Cell

26. Membuat Layout Utama
Buat folder **layout** di dalam **app/Views/**
Buat file **main.php** di dalam folder **layout** dengan kode berikut:

![image](https://github.com/user-attachments/assets/c3ea7d25-7e97-4c06-a53a-26b3a2acaa03)

![image](https://github.com/user-attachments/assets/0051ef7e-24f6-4740-97c2-96f3ec10341f)

27. Modifikasi File View
Ubah **app/Views/home.php** agar sesuai dengan layout baru:

![image](https://github.com/user-attachments/assets/e5a2fbb3-064e-470c-98b0-aafe29a15e31)

28. Membuat Class View Cell
Buat folder **Cells** di dalam **app/**
Buat file **ArtikelTerkini.php** di dalam **app/Cells/** dengan kode berikut:

![image](https://github.com/user-attachments/assets/6be0740b-4e46-430b-bab6-20207e85e7d5)

29. Membuat View untuk View Cell
Buat folder components di dalam **app/Views/**
Buat file **artikel_terkini.php** di dalam **app/Views/components/** dengan kode berikut:

![image](https://github.com/user-attachments/assets/d250d040-7b4e-4ad9-9d63-c59293f2ce9c)

30. Menambahkan tanggal
tujuanya agar mendapatkan data aertikel yang baru di ubah

![image](https://github.com/user-attachments/assets/313b69f7-f993-4487-82ce-22c9817fb689)

contohnya seperti ini :

![image](https://github.com/user-attachments/assets/88d73672-4819-47fa-8d32-1c22c1b740a7)

Apa manfaat utama dari penggunaan View Layout dalam pengembangan aplikasi?
jawab : 
1. Struktur yang Terorganisir
  - Memudahkan pengaturan elemen UI dengan tata letak yang rapi dan terstruktur.

2. Responsivitas yang Lebih Baik
  - Memastikan tampilan UI menyesuaikan dengan berbagai ukuran layar dan orientasi perangkat.

3. Pemeliharaan Kode yang Lebih Mudah
  - Dengan pemisahan tata letak dan logika bisnis, perubahan UI lebih mudah dilakukan tanpa mengganggu fungsionalitas aplikasi.
    
4. Penggunaan Ulang Komponen
  - Layout dapat digunakan kembali di berbagai bagian aplikasi, mengurangi redundansi kode.

5. Kinerja yang Lebih Optimal
  - Beberapa jenis layout dioptimalkan untuk performa yang lebih baik, seperti ConstraintLayout di Android yang mengurangi jumlah view hierarchy.

Jelaskan perbedaan antara View Cell dan View biasa.
jawab : 
![image](https://github.com/user-attachments/assets/3f08a236-4d3c-4d34-ab79-991e4f154339)

PRAKTIKUM KE 4
Untuk memulai membuat modul Login, yang perlu disiapkan adalah database server
menggunakan MySQL. Pastikan MySQL Server sudah dapat dijalankan melalui XAMPP.
![image](https://github.com/user-attachments/assets/612518c9-8902-46a3-87e8-4413f44dc013)


Membuat Model UserMembuat View Login
Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file baru
dengan nama login.php.
<!DOCTYPE html>
Selanjutnya adalah membuat Model untuk memproses data Login. Buat file baru pada direktori
app/Models dengan nama UserModel.php

Membuat View Login
Buat direktori baru dengan nama user pada direktori app/views, kemudian buat file baru
dengan nama login.php.
![image](https://github.com/user-attachments/assets/d0d1e79a-3681-4943-9516-fa0c1fef7615)

Membuat Database Seeder
Database seeder digunakan untuk membuat data dummy. Untuk keperluan ujicoba modul
login, kita perlu memasukkan data user dan password kedaalam database. Untuk itu buat
database seeder untuk tabel user. Buka CLI, kemudian tulis perintah berikut:
![image](https://github.com/user-attachments/assets/6a56ea2f-fd58-4012-bc5f-6e0968863d58)

Uji Coba Login
Selanjutnya buka url http://localhost:8080/user/login seperti berikut:
![image](https://github.com/user-attachments/assets/adaa150a-ebe1-4111-8250-920a9426d7d6)

Menambahkan Auth Filter
Selanjutnya membuat filer untuk halaman admin. Buat file baru dengan nama Auth.php pada
direktori app/Filters.
![image](https://github.com/user-attachments/assets/ece51c7f-2598-4566-8124-6a89b10528b6)

Selanjutnya buka file app/Config/Filters.php tambahkan kode berikut:
![image](https://github.com/user-attachments/assets/f2dc718d-bf9e-4ea3-9203-39148f08e61a)

Percobaan Akses Menu Admin
Buka url dengan alamat http://localhost:8080/admin/artikel ketika alamat tersebut diakses
maka, akan dimuculkan halaman login.
![image](https://github.com/user-attachments/assets/4d1f91ce-0096-4823-bd93-e41a6ce750c3)

Fungsi Logout
Tambahkan method logout pada Controller User seperti berikut:
![image](https://github.com/user-attachments/assets/2502b12b-c2d5-4d01-975b-9d568732eb57)

PRAKTIKUM KE 5
Untuk membuat pagination, buka Kembali Controller Artikel, kemudian modifikasi kode
pada method admin_index seperti berikut.
![image](https://github.com/user-attachments/assets/05c30a05-2fe1-4a96-9492-febee1a6d1dc)

Kemudian buka file views/artikel/admin_index.php dan tambahkan kode berikut
dibawah deklarasi tabel data.
![image](https://github.com/user-attachments/assets/c94cdff5-70f2-41cf-86f6-205938fec002)

Selanjutnya buka kembali menu daftar artikel, tambahkan data lagi untuk melihat
hasilnya.

Membuat Pencarian
Pencarian data digunakan untuk memfilter data.
Untuk membuat pencarian data, buka kembali Controller Artikel, pada method
admin_index ubah kodenya seperti berikut
![image](https://github.com/user-attachments/assets/333d5573-2bb6-48b7-a997-d49bc87282f8)

Kemudian buka kembali file views/artikel/admin_index.php dan tambahkan form
pencarian sebelum deklarasi tabel seperti berikut:
![image](https://github.com/user-attachments/assets/a49b2229-4d84-456f-9e58-71eb15ce81c0)

Selanjutnya ujicoba dengan membuka kembali halaman admin artikel, masukkan kata
kunci tertentu pada form pencarian.
![image](https://github.com/user-attachments/assets/f6867271-2c6e-4a4b-90aa-58a260dabf0d)

PRAKTIKUM 6: Upload File Gambar
Buka kembali Controller Artikel pada project sebelumnya, sesuaikan kode pada method
add seperti berikut:
![image](https://github.com/user-attachments/assets/7d7a9cc1-e932-4f29-b039-8a50dc804839)

Kemudian pada file views/artikel/form_add.php tambahkan field input file seperti
berikut.
![image](https://github.com/user-attachments/assets/81277268-1767-4cb8-8037-69d47029c629)

Ujicoba file upload dengan mengakses menu tambah artikel.
![image](https://github.com/user-attachments/assets/0ff83109-db06-42e2-a910-3e50241b6459)

PRAKTIKUM 7: Relasi Tabel dan Query Builder

1. Persiapan
Pastikan MySQL Server sudah berjalan, dan buka database `lab_ci4
2. Membuat Tabel Kategori
Kita akan membuat tabel baru bernama `kategori` untuk mengkategorikan artikel.
Struktur Tabel `kategori`:
![image](https://github.com/user-attachments/assets/bce94aee-ccb3-491c-a980-6f763669d0be)

3. Mengubah Tabel Artikel
Tambahkan foreign key `id_kategori` pada tabel `artikel` untuk membuat relasi dengan tabel
`kategori`.
Query untuk menambahkan foreign key:
![image](https://github.com/user-attachments/assets/ec1e10eb-28dc-44dd-bdee-1250a6f27335)

4. Membuat Model Kategori
Buat file model baru di `app/Models` dengan nama `KategoriModel.php`:
![image](https://github.com/user-attachments/assets/829b914f-4218-4f29-b8d6-5455bccc7a96)

5. Memodifikasi Model Artikel
Modifikasi `ArtikelModel.php` untuk mendefinisikan relasi dengan `KategoriModel`:
![image](https://github.com/user-attachments/assets/365753cb-8f48-4f80-9f9d-1660be1528b0)

6. Memodifikasi Controller Artikel
Modifikasi `Artikel.php` untuk menggunakan model baru dan menampilkan data relasi:
![image](https://github.com/user-attachments/assets/d125cc27-66fe-4c75-83eb-24ebbf40ac0d)
![image](https://github.com/user-attachments/assets/ec3d75e6-880c-47e6-a100-4fc88903a5ce)
![image](https://github.com/user-attachments/assets/fe5c1ddc-f049-4337-b718-7156a77231f4)
![image](https://github.com/user-attachments/assets/969f0a1b-810c-478f-b89a-c678484ed8ad)
![image](https://github.com/user-attachments/assets/37263b44-d9f2-46a2-a34e-dbfc4e623334)
![image](https://github.com/user-attachments/assets/bcb806ef-f63e-4f4f-bbc3-95643b811837)
![image](https://github.com/user-attachments/assets/8195da1b-c871-4d79-ab16-91d0eea6ed0f)
![image](https://github.com/user-attachments/assets/f1d1661b-dfe5-4bc0-aab2-a7e72666f80c)
![image](https://github.com/user-attachments/assets/36c7dff9-68ec-49de-a6fb-e46b5bcb74b7)
![image](https://github.com/user-attachments/assets/5408a514-8185-4d49-afeb-0841224e97ac)
![image](https://github.com/user-attachments/assets/f3744106-5010-4cb2-988e-40c37a4ec8a8)

7. Memodifikasi View
Buka folder view/artikel sesuaikan masing-masing view.
index.php
![image](https://github.com/user-attachments/assets/82c3e8f9-5a51-457b-bc34-3ecaf43ac5d6)

admin_index.php
![image](https://github.com/user-attachments/assets/b43481da-6c0d-4b3e-8c98-ae555e5b8f71)

form_add.php
![image](https://github.com/user-attachments/assets/2784b681-1fc1-4e48-843d-c6bbfe5715e3)

form_edit.php
![image](https://github.com/user-attachments/assets/9e589cd5-60e7-4310-9403-1fede0558dc9)

