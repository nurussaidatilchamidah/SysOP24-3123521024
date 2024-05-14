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


