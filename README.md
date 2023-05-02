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