# tugas pertemuan-12 <br>
## concurrent vs serial <br>
![Gambar WhatsApp 2024-05-14 pukul 09 01 08_436c0a85](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/423603f4-f402-4e4c-a092-9bb1dea16193) <br>
perbedaan antara concurrent dan serial seperti pada gambar diatas adalah : <br>
- Concurrent (Bersamaan) <br>
-- Definisi :<br>
Pemrosesan concurrent adalah metode di mana beberapa tugas atau instruksi dapat berjalan bersamaan. Ini bisa terjadi secara paralel atau melalui pengalihan konteks yang cepat. <br>
-- Cara Kerja : <br>
Tugas-tugas dapat berjalan secara bersamaan, baik dalam satu prosesor melalui pengalihan konteks atau pada beberapa prosesor/inti secara paralel. Tugas-tugas mungkin tidak selesai dalam urutan yang dimulai, tergantung pada alokasi waktu dan sumber daya. <br>
-- Contoh : <br>
Misalkan ada tiga tugas: A, B, dan C. Dalam pemrosesan concurrent, A, B, dan C dapat dimulai bersamaan dan berjalan secara tumpang tindih. Tugas A bisa selesai setelah B dan C dimulai, atau bahkan setelah C selesai, tergantung pada jadwal eksekusi. <br>
-- Keuntungan : <br>
Meningkatkan efisiensi penggunaan CPU karena beberapa tugas dapat dijalankan secara simultan dan dapat mempercepat waktu eksekusi secara keseluruhan, terutama pada sistem multi-core atau multi-prosesor. <br>
-- Kekurangan : <br>
Implementasi lebih kompleks karena perlu menangani sinkronisasi dan komunikasi antar-tugas dan meningkatkan risiko kondisi balapan (race conditions) di mana beberapa tugas mengakses data yang sama secara bersamaan tanpa sinkronisasi yang tepat. <br>

-  Serial <br>
-- Definisi : <br>
Pemrosesan serial adalah metode di mana tugas-tugas atau instruksi dijalankan satu per satu dalam urutan tertentu. Tidak ada dua tugas yang berjalan bersamaan pada satu waktu. <br>
-- Cara Kerja : <br>
Setiap tugas menunggu tugas sebelumnya selesai sebelum mulai. Proses dilakukan dalam urutan yang ditentukan, tanpa tumpang tindih. <br>
-- Contoh : <br>
Misalkan ada tiga tugas: A, B, dan C. Dalam pemrosesan serial, urutan eksekusinya akan selalu A, lalu B, dan kemudian C. <br>
-- Keuntungan : <br>
Implementasi sederhana karena tidak memerlukan sinkronisasi antar tugas. Debugging lebih mudah karena tidak ada interaksi yang kompleks antara tugas-tugas. <br>
-- Kekurangan : <br>
Kurang efisien dalam memanfaatkan sumber daya CPU, terutama pada sistem multi-core. Tidak ideal untuk aplikasi yang membutuhkan kinerja tinggi atau real-time processing. <br>

## concurrent vs parallel <br>
![Gambar WhatsApp 2024-05-14 pukul 09 03 30_0a841ab3](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/e47b3f1d-adb2-4989-bfd2-32748fd20d5b) <br>
perbedaan antara concurrent dan parallel seperti gambar diatas adalah : <br>
- Concurrent (Bersamaan) <br>
-- Definisi : <br>
Pemrosesan concurrent berarti beberapa tugas dijalankan dalam periode waktu yang sama. Tugas-tugas ini dapat dijalankan dalam urutan yang tumpang tindih, tetapi tidak selalu pada saat yang sama. Ini dapat dicapai melalui multitasking, di mana sistem operasi mengalihkan perhatian CPU dari satu tugas ke tugas lainnya dengan cepat. <br>
-- Cara Kerja : <br>
Multitasking: CPU mengalihkan konteks antara tugas-tugas, memberikan ilusi bahwa tugas-tugas tersebut berjalan bersamaan. Cocok untuk aplikasi yang memerlukan interaktivitas tinggi atau harus merespons beberapa kejadian (events) secara bersamaan. <br>
-- Contoh : <br>
Sebuah server web yang menangani beberapa permintaan klien secara bersamaan. Meskipun setiap permintaan tidak selalu diproses secara paralel, server dapat mengelola banyak permintaan secara concurrent. <br>
-- Keuntungan : <br>
Dapat membuat aplikasi lebih responsif dan mengoptimalkan penggunaan waktu idle CPU. <br>
-- Kekurangan : <br>
Lebih kompleks untuk diimplementasikan dan membutuhkan manajemen yang baik terhadap sinkronisasi antar tugas. <br>

- Parallel (Paralel) <br>
-- Definisi : <br>
Pemrosesan parallel berarti beberapa tugas benar-benar berjalan pada saat yang sama. Ini memerlukan beberapa unit pemrosesan (seperti multiple cores atau multiple processors) yang bekerja bersamaan. <br>
-- Cara Kerja : <br>
Parallelisme terjadi ketika beberapa prosesor atau inti CPU menjalankan tugas yang berbeda pada saat yang sama. Cocok untuk tugas-tugas yang dapat dipecah menjadi subtugas independen yang dapat dijalankan secara simultan. <br>
-- Contoh : <br>
Pengolahan gambar, di mana setiap bagian dari gambar dapat diproses secara paralel pada inti CPU yang berbeda dan Algoritma pembelajaran mesin yang melakukan komputasi intensif dapat didistribusikan ke banyak GPU untuk eksekusi paralel. <br>
-- Keuntungan : <br>
Dapat sangat mempercepat eksekusi tugas-tugas berat yang dapat dipecah menjadi bagian-bagian yang lebih kecil dan independen. Efisiensi tinggi pada sistem dengan banyak inti atau prosesor. <br>
-- Kekurangan : <br>
Memerlukan perangkat keras khusus yang mendukung eksekusi paralel. Lebih sulit untuk diimplementasikan dan di-debug dibandingkan dengan pemrosesan serial atau concurrent. <br>



