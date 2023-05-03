# django4_sosmed_with_react
Membuat Aplikasi Sosmed Menggunakan Django 4 dan React 18

[Gihub repo](https://github.com/gurnitha/django4_sosmed_with_react)


## 0. Setup - Create Github Repository


## 1. Creating a Django Project


#### 1.1. Sekilas tentang pengembangan perangkat lunak


        Sekilas tentang pengembangan perangkat lunak

        Pengembangan perangkat lunak adalah proses kompleks yang penuh dengan banyak langkah dan banyak komponen. 
        Komponen-komponen ini memastikan bahwa menyusun, menentukan, merancang, memprogram, mendokumentasikan, 
        dan menguji aplikasi, Kerangka kerja, atau perangkat lunak dihormati dan diterapkan dengan baik. 

        Secara umum, perangkat lunak dibuat dari dua komponen berikut:

        • Backend: Ini menunjukkan apa yang tidak dapat dilihat oleh pengguna; itu terdiri dari logika bisnis dan manipulasi data dari database
        • The frontend: Ini merupakan antarmuka yang disediakan untuk pengguna untuk berinteraksi dengan seluruh aplikasi


#### 1.2. Memahami pengembangan backend


        Memahami pengembangan backend

        Pengembangan backend menangani aplikasi modern di balik layar. Sebagian besar waktu,
        itu terbuat dari kode yang terhubung ke database, mengelola koneksi pengguna, dan juga mendukung web
        aplikasi atau API.

        Fokus kode pengembangan backend lebih pada logika bisnis. Ini terutama berfokus pada bagaimana
        Aplikasi berfungsi dan fungsionalitas serta logika yang menggerakkan aplikasi.

        Misalnya, mari kita bicara tentang aplikasi web yang dibuat untuk mengelola buku. Mari kita anggap bahwa aplikasi
        terhubung ke database SQL.

        Bahasa apa pun yang digunakan untuk membangun aplikasi dan strukturnya, berikut beberapa persyaratannya
        yang mewakili logika bisnis dan yang terutama bergantung pada backend daripada frontend:

        • Menambahkan buku (hanya untuk admin): Ini mengandaikan bahwa klien (frontend) harus bisa
        buat permintaan ke API yang diberdayakan menggunakan bahasa apa pun yang dibuat untuk backend, berisi
        data yang diperlukan untuk membuat entri baru dalam database yang mewakili sebuah buku. Tindakan ini
        hanya tersedia untuk admin.
        • Mencantumkan semua buku: Ini mengandaikan bahwa klien juga harus dapat membuat permintaan ke API,
        dan API ini harus mengirimkan sebagai tanggapan daftar semua buku dalam format JSON/XML.

        Hanya dengan melihat kedua persyaratan ini, kita dapat dengan cepat memahami bahwa frontend akan adil
        menjadi antarmuka untuk meminta tindakan ini. Namun, backend akan (mengambil yang pertama
        persyaratan sebagai contoh) pastikan bahwa permintaan yang masuk dimungkinkan (memeriksa izin
        seperti apakah pengguna yang membuat permintaan benar-benar seorang admin) dan bahwa data dalam permintaan tersebut valid
        – hanya setelah itu data dapat didaftarkan dengan aman di database.


#### 1.3. Tanggung jawab pengembang backend

        Tanggung jawab pengembang backend

        Backend biasanya terbuat dari tiga bagian utama:

        • Server: Mesin atau aplikasi (NGINX) yang menerima permintaan
        • Aplikasi: Aplikasi yang berjalan di server yang menerima permintaan, memvalidasi permintaan ini, dan mengirimkan respons yang sesuai.
        • Database: Digunakan untuk menyimpan data

        Dengan demikian, tanggung jawab pemrogram backend dapat dengan mudah melibatkan penulisan API, menulis kode untuk berinteraksi dengan database, membuat modul atau pustaka, juga mengerjakan data dan arsitektur bisnis, dan banyak lagi.

        Mereka juga harus melakukan hal berikut:

        • Berkoordinasi dan berkomunikasi dengan pengembang frontend untuk mentransfer data secara efisien ke sisi klien aplikasi.
        • Berkolaborasi dengan teknisi jaminan kualitas untuk mengoptimalkan proses sisi server dan juga lulus beberapa pemeriksaan keamanan
        • Mengoptimalkan aplikasi saat jumlah permintaan atau pengguna juga meningkat
        • Menganalisis persyaratan proyek dan membuat struktur sederhana untuk menangani bug dan kesalahan.
        • Mengusulkan solusi yang efisien untuk cloud hosting tetapi juga membangun pipeline CI/CD Arsitektur backend sebenarnya membantu membangun salah satu antarmuka yang paling umum untuk menggunakan data dalam industri perangkat lunak: Application Programming Interface (API). Mari kita pelajari lebih lanjut tentang istilah tersebut.


#### 1.4. Apa itu API?

        Ingatlah bahwa sebagian besar internet didukung oleh Representational State Transfer (REST) atau RESTful API. API menyederhanakan cara pertukaran data antara aplikasi atau mesin.

        Ini terutama terdiri dari dua komponen:

        • Spesifikasi teknis yang menjelaskan tentang opsi pertukaran data antara para pihak, dengan spesifikasi yang dibuat dalam bentuk permintaan protokol pengiriman data dan pemrosesan data
        • Antarmuka perangkat lunak (kode pemrograman), yang ditulis sesuai spesifikasi yang mewakilinya. Misalnya, jika sisi klien aplikasi Anda ditulis dalam JavaScript dan sisi server ditulis dalam PHP, Anda harus membuat web API dengan PHP (karena data berasal dari database), yang akan membantu Anda menulis aturan dan rute yang akan digunakan untuk mengakses data.

        API Web relatif umum dan ada spesifikasi dan protokol yang berbeda.


#### 1.5.Memahami REST API

        Memahami REST API

        REST biasanya merupakan cara yang harus dilakukan ketika pengembang ingin membangun API. REST adalah alternatif sederhana untuk SOAP dan RPC, karena memudahkan penulisan logika untuk mengakses sumber daya; sumber daya di sini diwakili oleh URL unik yang tersedia dengan satu permintaan ke URL ini.

        RESTful API menggunakan permintaan HTTP (atau metode) untuk berinteraksi dengan sumber daya:

        • DAPATKAN: Metode yang paling umum digunakan di API dan situs web. Metode ini digunakan untuk mengambil data dari server pada sumber daya tertentu. Sumber daya ini adalah titik akhir yang mengembalikan objek atau daftar objek di JSON atau XML sebagian besar waktu.

        • POST: Metode POST adalah metode dasar untuk meminta pemrosesan informasi dari server. Permintaan ini seharusnya membawa mekanisme khusus ke server dan menyebabkan komunikasi dengan modul lain, atau bahkan server lain, untuk memproses data tersebut. Karena itu, sangat mungkin bahwa dua permintaan POST yang identik akan menerima yang berbeda atau bahkan secara semantik respon berlawanan. Data yang akan diproses ditentukan dalam isi permintaan. Itu dokumen yang ditunjuk oleh permintaan melalui halaman adalah sumber daya yang harus memproses data dan menghasilkan respon.

        • HEAD: Metode HEAD digunakan untuk menanyakan header respons, tanpa file dikirim kepada Anda segera. Ini berguna, misalnya, jika file besar perlu ditransfer: terima kasih untuk permintaan HEAD, klien dapat diberi tahu tentang ukuran file terlebih dahulu dan baru kemudian memutuskan apakah akan menerima file.

        • PILIHAN: Ini adalah metode diagnostik, yang mengembalikan pesan yang berguna terutama untuk debugging dan sejenisnya. Pesan ini pada dasarnya menunjukkan, secara mengejutkan, metode HTTP mana aktif di web server. Pada kenyataannya, itu jarang digunakan untuk tujuan yang sah akhir-akhir ini, tetapi itu memang memberikan sedikit bantuan kepada penyerang potensial – ini dapat dilihat sebagai jalan pintas untuk menemukan lubang lain.

        • HAPUS dan PUT: Metode ini seharusnya memungkinkan dokumen untuk diunggah (ke file server) atau dihapus tanpa melalui server File Transfer Protocol (FTP) atau sejenisnya. Jelas, ini dapat menyebabkan penggantian file, dan karenanya pelanggaran keamanan yang sangat besar di server. Oleh karena itu, sebagian besar server web memerlukan konfigurasi khusus dengan sumber daya atau dokumen bertanggung jawab untuk memproses permintaan ini. Dokumen yang dirujuk oleh permintaan adalah dokumen untuk diganti (atau dibuat), dan isi dokumen ada di badan permintaan. Secara teori, Parameter URL dan pengidentifikasi fragmen harus dilarang atau diabaikan oleh server. Di dalam praktek, mereka umumnya ditransmisikan ke sumber daya yang bertanggung jawab untuk memproses permintaan tersebut.

        • PATCH: Metode PATCH dari permintaan HTTP menerapkan sebagian perubahan pada sumber daya.

        • TRACE: Metode TRACE dapat digunakan untuk melacak jalur yang diambil oleh permintaan HTTP ke server dan kemudian ke klien.

        • CONNECT: Metode ini seharusnya digunakan untuk meminta penggunaan server sebagai proxy. Bukan semua server harus mengimplementasikannya. Satu manfaat yang menarik adalah sistem RESTful mendukung format data yang berbeda, seperti teks biasa, HTML, YAML, JSON, dan XML. Seperti disebutkan sebelumnya, dalam buku ini, kita akan membuat REST API menggunakan Django dan Django REST


#### 1.6. Apa itu Django?

        Apa itu Django?

        Django adalah kerangka web lanjutan yang pertama kali dirilis pada tahun 2005. Ini ditulis dengan Python dan menggunakan pola arsitektur Model-View-Controller (MVC). Pola ini umum didefinisikan sebagai berikut:

        • Model: Sesuai dengan semua logika terkait data. Ini sangat terhubung ke database, seperti itu menyediakan bentuk data tetapi juga metode dan fungsi untuk Buat, Baca, Perbarui, dan Hapus (CRUD) operasi.

        • View: Menangani logika UI aplikasi.

        • Controller: Merupakan lapisan antara model dan tampilan. Sebagian besar waktu, pengemudi menafsirkan permintaan yang masuk dari tampilan, memanipulasi data yang disediakan oleh model komponen, dan berinteraksi dengan tampilan lagi untuk membuat hasil akhir.

        In Django, this will be referred to as the Model-View-Template (MVT) architecture with the template corresponding to the view and the view here represented by the controller.


#### 1.7. Menyiapkan lingkungan kerja

        Menyiapkan lingkungan kerja

        Sebelum mulai bekerja dengan Django, kami harus memastikan Anda memiliki lingkungan yang bagus, apa pun OS nya yang Anda gunakan saat ini.

        Pertama-tama, pastikan Anda menginstal Python versi terbaru. Untuk buku ini, kami akan bekerja dengan Python 3.9.5.

        Jika Anda menggunakan mesin Windows, buka halaman unduhan resmi di https://www.python. org/downloads/ dan unduh versi yang relevan. 

        Untuk pengguna Linux, Anda dapat mengunduhnya menggunakan pengelola unduhan paket repositori default.


#### 1.8. Creating a virtual environment

        Menciptakan lingkungan virtual

        Sekarang kita telah menginstal Python, kita harus memastikan bahwa kita telah menginstal virtualenv:

        > python3 -m pip install --user virtualenv

        Lihat yang berikut untuk pengguna Windows:

        > py -m pip install --user virtualenv

        Setelah ini selesai, kita sekarang dapat membuat lingkungan virtual – tetapi mengapa?

        Ada dua jenis lingkungan saat mengembangkan dengan Python: lingkungan global dan lingkungan lokal.

        Jika Anda hanya memasukkan permintaan instal pip secara acak di terminal, paket akan diinstal dan dapat diakses secara global: ini berarti diakses di mana saja di mesin Anda. Terkadang Anda ingin menyendiri lingkungan kerja untuk menghindari konflik versi. Misalnya, secara global Anda mungkin bekerja dengan Python 3.5, yang mendukung versi Django 2.x. Namun, untuk proyek ini, Anda ingin menggunakan Python 3.10 dan versi terbaru Django – di sini, 4.0. Membuat lingkungan virtualenv membantu Anda dengan itu.

        Sekarang kita telah menginstal virutalenv, kita dapat membuat dan mengaktifkan lingkungan virtualenv – tetapi sebelum itu, buat sebuah direktori bernama django-api. Kami akan membangun proyek Python di sini.

        Lihat yang berikut untuk Unix atau macOS:

        > python3 -m venv venv3942

        venv3942 dimaksudkan untuk mengetahui bahwa proyek ini menggunakan Python versi 3.10 dan Django 4.2

        Lihat yang berikut untuk Windows:

        > py -m venv venv3942

        Perintah-perintah sebelumnya ini akan membuat direktori venv3942 yang berisi paket-paket Python yang diinstal dan konfigurasi yang diperlukan untuk mengakses paket ini saat lingkungan virtual diaktifkan. Langkah selanjutnya adalah mengaktifkan lingkungan virtual. Ini akan membantu kami menginstal paket yang kami perlukan mulai bekerja.

        Lihat yang berikut untuk Unix atau macOS:

        > source venv3942/bin/activate

        Lihat yang berikut untuk Windows:

        > .\venv3942\Scripts\activate

        Hebat! Selanjutnya, mari instal paket Django.


#### 1.9 Menginstal Django

        Menginstal Django

        Ada dua cara untuk menginstal paket dengan Python. Anda dapat dengan mudah menjalankan pip install package_name.

        Cara lainnya, Anda dapat menulis nama paket dengan versinya dalam file teks. Saya akan menggunakan yang pertama tetapi jangan ragu untuk menggunakan versi apa pun yang cocok untuk Anda.

        Saya akan memulainya:

        # Memeriksa versi python, pip dan virtualenv

        > python --version
        > pip --version
        > virtualenv --vesion

        # Membuat local virtual environment

        > python -m venv venv3942

        # Meng-upgrade pip

        > python -m install pip --upgrade pip

        # Menginstl django versi 4.2

        > venv3942\Scripts\activate
        > (venv3942) pip install django==4.2

        # Memeriksa hasil instalasi

        > pip list

        Package    Version
        ---------- -------
        asgiref    3.6.0
        Django     4.2
        pip        23.1.2
        setuptools 56.0.0
        sqlparse   0.4.4
        tzdata     2023.3

        Django versi 4.2 telah berhasil diinstal


#### 1.10. Membuat proyek sampel

        Membuat proyek sampel

        Untuk membuat proyek baru, kita akan menggunakan perintah django-admin. Itu datang dengan opsi yang bisa kita gunakan untuk membuat proyek di Django:

        > django-admin memulai proyek CoreRoot .

        Jangan lupa untuk menambahkan . titik di akhir perintah ini. Ini benar-benar akan menghasilkan semua file di direktori saat ini alih-alih membuat direktori lain untuk memasukkan semua file.

        Anda harus memiliki struktur file seperti ini:
        .
        ├── CoreRoot
        │   ├── __init__.py
        │   ├── asgi.py
        │   ├── settings.py
        │   ├── urls.py
        │   └── wsgi.py
        ├── README.md
        └── manage.py

        Sebelum memulai server, mari jalankan migrasi:

        > python manage.py makemigrations
        > python manage.py migrate

        Anda akan memiliki keluaran yang serupa:

        Operations to perform:
          Apply all migrations: admin, auth, contenttypes, sessions
        Running migrations:
          Applying contenttypes.0001_initial... OK
          Applying auth.0001_initial... OK
          Applying admin.0001_initial... OK
          Applying admin.0002_logentry_remove_auto_add... OK
          Applying admin.0003_logentry_add_action_flag_choices... OK
          Applying contenttypes.0002_remove_content_type_name... OK
          Applying auth.0002_alter_permission_name_max_length... OK
          Applying auth.0003_alter_user_email_max_length... OK
          Applying auth.0004_alter_user_username_opts... OK
          Applying auth.0005_alter_user_last_login_null... OK
          Applying auth.0006_require_contenttypes_0002... OK
          Applying auth.0007_alter_validators_add_error_messages... OK
          Applying auth.0008_alter_user_username_max_length... OK
          Applying auth.0009_alter_user_last_name_max_length... OK
          Applying auth.0010_alter_group_name_max_length... OK
          Applying auth.0011_update_proxy_permissions... OK
          Applying auth.0012_alter_user_first_name_max_length... OK
          Applying sessions.0001_initial... OK

        Migrasi hanyalah cara untuk menyebarkan perubahan yang dilakukan pada model dalam skema database. Karena Django juga hadir dengan beberapa model (seperti model Pengguna yang dapat Anda gunakan untuk autentikasi), kita perlu menerapkan migrasi ini. Saat kita menulis model kita sendiri, kita juga akan membuat file migrasi dan memigrasikannya. Django memiliki object-relational mapping (ORM) yang secara otomatis menangani interaksi dengan basis data untuk Anda.

        Mempelajari SQL dan menulis kueri Anda sendiri cukup sulit dan menuntut saat Anda baru mengenalnya. Butuh waktu lama dan cukup merepotkan. Untungnya, Django menyediakan sistem untuk mengambil manfaat dari database SQL tanpa harus menulis bahkan kueri SQL tunggal!

        Jenis sistem ini disebut ORM. Di balik nama yang terdengar agak biadab ini menyembunyikan operasi yang sederhana dan sangat berguna. Saat Anda membuat model di aplikasi Django Anda, kerangka kerja akan secara otomatis membuat tabel yang sesuai di basis data yang akan menyimpan data yang berkaitan dengan model.

        Tidak perlu menulis perintah SQL di sini – kita hanya akan menulis kode dengan Python yang akan langsung diterjemahkan ke dalam SQL. python manage.py migrate kemudian akan menerapkan perubahan ini ke database.

        Sekarang, jalankan python manage.py runserver. Anda akan melihat keluaran yang serupa, dan server Anda juga akan berjalan di https://localhost:8000.

        Tekan saja URL https://localhost:8000 di browser Anda dan Anda akan melihat sesuatu yang laur biasa: default landing page dari Django.

        Jika Anda melihathanya pada browser Anda, maka Anda telah berhasil.

        Selamat!

        Mari kita bahas contoh proyek yang telah berhasil kita buat.

        Hebat – kita baru saja menginstal Django dan memulai server Django. Mari kita bicara tentang struktur proyek.

        Di bagian terakhir, kita telah membahas secara singkat tentang cara membuat lingkungan virtualenv dengan Python. kita juga telah membuat proyek Django dan menjalankannya.

        Mari kita bicara dengan cepat tentang proyek ini.

        Anda mungkin memperhatikan beberapa berkas dan direktori di direktori django-api. Baiklah, mari kita bicarakan ini dengan cepat:

        • manage.py: Ini adalah utilitas yang disediakan oleh Django untuk berbagai kebutuhan. Ini akan membantu Anda membuat proyek dan aplikasi, menjalankan migrasi, memulai server, dan seterusnya.
        • CoreRoot: Ini adalah nama proyek yang telah kita buat dengan perintah django-admin. Ini berisi file-file seperti berikut:

          • urls.py: Ini berisi semua URL yang akan digunakan untuk mengakses sumber daya dalam proyek:

            from django.contrib import admin
            from django.urls import path
            urlpatterns = [
                  path('admin/', admin.site.urls),
            ]

          • wsgi.py: File ini pada dasarnya digunakan untuk penyebaran tetapi juga sebagai pengembangan default lingkungan di Django.
          • asgi.py: Django juga mendukung menjalankan kode asinkron sebagai aplikasi ASGI.
          • settings.py: Ini berisi semua pengaturan untuk proyek Django Anda. kamu dapat menemukan SECRET_KEY, daftar INSTALLED_APPS, ALLOWED_HOST, dan seterusnya.

          Sekarang anda familiar dengan struktur proyek Django. Selanjutnya mari kita lihat bagaimana mengkonfigurasi proyek untuk terhubung ke database.

        File baru:

        modified:   .gitignore
        new file:   CoreRoot/__init__.py
        new file:   CoreRoot/asgi.py
        new file:   CoreRoot/settings.py
        new file:   CoreRoot/urls.py
        new file:   CoreRoot/wsgi.py
        modified:   README.md


#### 1.11. Mengkonfigurasi basis data

        Mengkonfigurasi basis data

        Django, secara default, menggunakan sqlite3 sebagai basis data, yang merupakan pustaka dalam proses (in-process library) yang mengimplementasikan mesin basis data SQL mandiri, tanpa konfigurasi, tanpa server, dan transaksional cepat. Ini sangat kompak dan mudah digunakan dan diatur. Ini ideal jika Anda ingin menyimpan data dengan cepat atau untuk pengujian. Namun, ia datang dengan beberapa kelemahan.

        Pertama-tama, tidak ada kemampuan multi-pengguna, yang berarti ia hadir dengan kurangnya kontrol akses granular dan beberapa kemampuan keamanan. Ini karena fakta bahwa SQLite membaca dan menulis langsung ke file disk biasa.

        Misalnya, dalam proyek kita, setelah menjalankan migrasi, Anda akan melihat pembuatan file baru, db.sqlite3. Nah, ini database kita sebenarnya. Kita akan menggantinya dengan SMDB yang lebih kuat bernama Postgres.