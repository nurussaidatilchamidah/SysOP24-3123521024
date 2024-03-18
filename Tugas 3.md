# Tugas 3
**1. Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program. Jelaskan juga peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operasi.**

#### Siklus CPU: Fetch, Decode, Execute
- Fetch (Ambil) <br>
a. Proses dimulai dengan CPU mengambil instruksi dari memori utama (RAM) ke dalam register instruksi. <br>
b. Alamat instruksi disediakan oleh program counter (PC). <br>
c. Instruksi tersebut akan diambil ke dalam register instruksi untuk proses selanjutnya.

- Decode (Dekode) <br>
a. Instruksi yang diambil dari memori di-dekode oleh CPU. <br>
b. CPU menafsirkan instruksi tersebut untuk mengetahui operasi apa yang harus dilakukan. <br>
c. Dekoding melibatkan memahami opcode (kode operasi) dan operand (data yang diperlukan untuk operasi).

- Execute (Eksekusi) <br>
a. Setelah instruksi di-dekode, CPU mengeksekusi operasi yang ditentukan oleh instruksi tersebut. <br>
b. Operasi bisa berupa manipulasi data, pemrosesan logika, pengambilan keputusan, atau transfer data antar register atau memori.

#### Peran Bahasa Pemrograman : 
Bahasa pemrograman adalah cara bagi manusia untuk berkomunikasi dengan komputer. Memungkinkan programmer menulis kode dengan menggunakan struktur dan sintaks tertentu yang dapat dimengerti oleh komputer. Bahasa pemrograman menyediakan berbagai fitur dan abstraksi untuk memudahkan pengembangan perangkat lunak.

#### Peran Compiler : 
Compiler adalah perangkat lunak yang menerjemahkan kode sumber dalam bahasa pemrograman tingkat tinggi menjadi kode mesin yang dapat dimengerti oleh komputer. Compiler mengubah kode sumber menjadi bentuk yang dapat dieksekusi oleh CPU. Ini melibatkan proses analisis sintaksis, optimasi, dan pembuatan kode objek.

#### Peran Sistem Operasi : 
Sistem operasi (OS) bertindak sebagai perantara antara perangkat keras komputer dan perangkat lunak aplikasi. Mengelola sumber daya sistem seperti CPU, memori, dan perangkat input/output. Menyediakan antarmuka untuk berbagai fungsi sistem, termasuk manajemen file, multitasking, keamanan, dan jaringan. Sistem operasi memfasilitasi eksekusi program dengan mengatur alokasi sumber daya dan menjalankan proses secara efisien.

**3. menjalankan debian**

- melakukan clone ke https://github.com/ferryastika/flops-iops dan masuk ke direktori flops-iops
  
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/64d1c1a7-f962-47da-85c2-1eae0a05d328)

- $ make
- $ make clean
- $ sudo make install
- $ sudo make uninstall
  
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/94fb7976-3326-47a1-a1de-5ebf846bdb2a)

- percobaan 1

$ iops64 $(nproc) <br>
$ flops64 $(nproc)

![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/ae9f3931-f027-4f1e-a9dc-c24c13767894)

- percobaan 2

$ iops64 $(nproc) <br>
$ flops64 $(nproc)

![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/715f822a-6edb-4f91-adfd-bd8ad793f04d)

- percobaan 3
  
$ iops64 $(nproc) <br>
$ flops64 $(nproc)

![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/e178c817-968b-467e-b4f2-d603778434f7)

- percobaan 4
  
$ iops64 $(nproc) <br>
$ flops64 $(nproc)

![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/8ee63d75-3317-4e95-8b9c-1eb376517c5a)


- percobaan 5
  
$ iops64 $(nproc) <br>
$ flops64 $(nproc)

![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/8dc627e3-e9e9-42aa-a8d3-7d14324d8135)

#### Perbandingan hasil iops dan flops antar teman

![Gambar WhatsApp 2024-03-18 pukul 16 58 09_6f97b20f](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/91d08e54-7175-4dc5-aeba-8625f83c24af)

- Analisa :
    - $iops64: Ini mengukur berapa kali sistem dapat melakukan operasi input/output dalam satu detik. Hasil yang tinggi menunjukkan kemampuan sistem untuk menangani beban kerja IO yang berat dengan efisien. Jika hasilnya rendah, itu mungkin menunjukkan adanya bottleneck dalam penyimpanan atau struktur sistem file.
    - $flops64: Ini mengukur seberapa cepat sistem dapat melakukan operasi floating point dalam satu detik. FLOPS penting dalam aplikasi yang memerlukan komputasi intensif, seperti simulasi ilmiah atau analisis data besar. Hasil yang tinggi menunjukkan kemampuan sistem untuk menyelesaikan tugas komputasi dengan cepat. 

- Kesimpulan : 
dari hasil percobaan $iops64 dan flops64 diatas, meira memiliki rata-rata yang tinggi dibanding dengan yang lain, hal itu menunjukkan sistem mampu menangani beban kerja IO dan komputasi dengan lebih baik. Namun, jika salah satu atau kedua hasilnya rendah, itu mungkin menunjukkan adanya pembatasan kinerja dalam sistem tersebut yang perlu diperbaiki atau ditingkatkan.

**4. instalasi packeage gcc, make dan git**

- packeage gcc
  
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/29237bfd-58e4-4641-8324-cbec65585b29)

- make
  
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/d1965c42-2e57-45a6-b9d1-87a57281d172)

- git
  
 ![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/53c9082e-7dc6-4ecb-a1ee-9cc161ae1508)
 
   
     







  




  
