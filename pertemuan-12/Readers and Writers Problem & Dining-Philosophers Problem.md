# tugas pertemuan-12 <br>
## Readers and Writers Problem (masalah pembaca dan penulis) <br>
Masalah Pembaca-Penulis adalah masalah sinkronisasi klasik dalam sistem operasi (OS) dan pemrograman bersamaan. Ini berkisar pada tantangan mengelola sumber daya bersama, 
khususnya struktur data atau bagian kode, yang diakses oleh banyak thread. Masalah Pembaca-Penulis berkaitan dengan tantangan mengelola akses bersamaan terhadap sumber daya bersama oleh banyak pembaca dan satu penulis. Hal ini menekankan perlunya memberikan akses simultan kepada banyak pembaca untuk membaca sambil memastikan akses eksklusif untuk menulis guna menjaga integritas data. <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/8d4378fa-b54b-4f27-8a41-286f5b8ee3e2) <br>
**Bagaimana Masalah Pembaca-Penulis OS Ditangani?** <br>
Untuk menangani masalah ini, harus dipastikan bahwa tidak ada proses bersamaan yang menyebabkan segala bentuk ketidakkonsistenan data dalam sistem operasi. Masalah pembaca-penulis di os dapat diasumsikan sebagai berikut : <br> 
Ada beberapa proses yang dapat berupa pembaca dan penulis dengan sumber daya bersama di antara mereka, anggap saja sebagai file atau database. Jika ada dua proses dengan keduanya mencoba mengakses sumber daya secara bersamaan pada instance yang sama. Meskipun tidak peduli berapa banyak pembaca yang dapat mengaksesnya secara bersamaan, harus diingat bahwa hanya satu penulis yang dapat menulisnya dalam satu waktu. <br>
Mengatasi Masalah Pembaca-Penulis sangat penting dalam memastikan akses bersamaan yang efisien dan aman ke sumber daya bersama dalam sistem operasi. Memahami nuansa dan tantangan yang ditimbulkan oleh banyak pembaca dan penulis yang mengakses data yang sama secara bersamaan sangat penting untuk merancang sistem yang kuat dan terukur. Penggunaan teknik sinkronisasi dan algoritme yang disesuaikan dengan masalah ini dapat meningkatkan kinerja sistem secara signifikan sekaligus mencegah kerusakan dan inkonsistensi data. <br>

## Dining-Philosophers Problem <br>
Dalam ilmu komputer , masalah filsuf makan adalah contoh masalah yang sering digunakan dalam desain algoritma konkuren untuk menggambarkan masalah sinkronisasi dan teknik penyelesaiannya. <br>
**Pernyataan masalah :** <br>
Lima filsuf makan bersama di meja yang sama. Setiap filsuf memiliki piringnya sendiri di meja. Ada garpu di antara setiap piring. Hidangan yang disajikan sejenis spageti yang harus dimakan dengan dua garpu. Setiap filsuf hanya bisa berpikir dan makan secara bergantian. Terlebih lagi, seorang filsuf hanya bisa memakan spagetinya jika ia memiliki garpu kiri dan kanan. Dengan demikian dua garpu hanya akan tersedia ketika dua tetangga terdekatnya sedang berpikir, bukan makan. Setelah seorang filsuf selesai makan, dia akan meletakkan kedua garpunya. Masalahnya adalah bagaimana merancang sebuah regimen ( algoritma konkuren ) sedemikian rupa sehingga filsuf mana pun tidak akan kelaparan; yaitu , masing-masing dapat selamanya terus berganti-ganti antara makan dan berpikir, dengan asumsi bahwa tidak ada filsuf yang mengetahui kapan orang lain ingin makan atau berpikir <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/c8adc138-a714-480b-9dc4-d2c9a1ea571b) <br>
**Solusi penyelesaiannya :** <br>
Ada beberapa solusi untuk menyelesaikan masalah Dining Philosophers, masing-masing bertujuan untuk menghindari deadlock dan kelaparan : <br>
1. Solusi Hierarki Sumber Daya <br>
Tetapkan urutan numerik pada garpu (misalnya, Garpu 1, Garpu 2, ..., Garpu 5). Setiap filsuf harus mengambil garpu yang bernomor lebih rendah terlebih dahulu dan kemudian garpu yang bernomor lebih tinggi. <br>
2. Solusi Arbitrator <br>
Perkenalkan seorang arbitrator (mutex atau semaphore) yang mengontrol akses ke garpu. Seorang filsuf harus meminta izin dari arbitrator sebelum mengambil garpu. <br>
3. Solusi Chandy/Misra (Hierarki Sumber Daya dengan Token) <br>
Para filsuf mengambil garpu yang bernomor lebih rendah terlebih dahulu dan kemudian garpu yang bernomor lebih tinggi.
Ini menghindari deadlock karena memecah kondisi menunggu melingkar. <br>
4. Solusi Asimetris <br>
Para filsuf bernomor ganjil mengambil garpu kiri terlebih dahulu dan kemudian garpu kanan, sementara para filsuf bernomor genap mengambil garpu kanan terlebih dahulu dan kemudian garpu kiri. <br>


