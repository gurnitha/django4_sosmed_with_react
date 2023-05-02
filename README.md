# django4_sosmed_with_react
Membuat Aplikasi Sosmed Menggunakan Django 4 dan React 18

[Gihub repo](https://github.com/gurnitha/django4_sosmed_with_react)


## 0. Setup - Create Github Repository


## 1. Creating a Django Project


#### 1.1. An overview of software development

        modified:   README.md

        Sekilas tentang pengembangan perangkat lunak

        Pengembangan perangkat lunak adalah proses kompleks yang penuh dengan banyak langkah dan banyak komponen. 
        Komponen-komponen ini memastikan bahwa menyusun, menentukan, merancang, memprogram, mendokumentasikan, 
        dan menguji aplikasi, Kerangka kerja, atau perangkat lunak dihormati dan diterapkan dengan baik. 

        Secara umum, perangkat lunak dibuat dari dua komponen berikut:

        • Backend: Ini menunjukkan apa yang tidak dapat dilihat oleh pengguna; itu terdiri dari logika bisnis dan manipulasi data dari database
        • The frontend: Ini merupakan antarmuka yang disediakan untuk pengguna untuk berinteraksi dengan seluruh aplikasi


#### 1.2. Understanding backend development


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