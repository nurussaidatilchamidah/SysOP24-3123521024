# Tugas 3.1
**1. Buatlah presentasi langkah demi langkah tentang siklus CPU (fetch,decode,execute) utk mengeksekusi sebuah program. Jelaskan juga peran dari Bahasa pemrograman dan compiler, begitu juga dengan peran dari Sistem Operasi.**

#### Siklus CPU: Fetch, Decode, Execute <br>
Central Processing Unit atau CPU terhubung ke semua perangkat lain yang membuatnya berfungsi. setiap detik, CPU melewati langkah yang disebut Fetch-Decode-Execute. Di CPU memiliki 3 register : bit penyimpanan (tempat menyimpan nilai-nilai yang sedang dikerjakan saat ini), register yang melacak siklus instruksi kita, dan akumulator. lalu, tempat untuk menyimpan intruksi dan nilai apapun yang kita hitung disebut RAM. <br>
Pada setiap detik, CPU akan melakukan salah satu dari tiga hal berikut :
- Fetch (Ambil) <br>
- Decode (Memecahkan) <br>
- Execute (Eksekusi) <br>

![0](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/02511fe1-6442-4534-80ce-108b4d174beb)

##### [ Fetch, program counter diatur ke 0, lalu CPU mengambil intruksi pada alamat 0 di memori dan memasukkannya ke dalam register intruksi ]
![1](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/348667de-56c0-45be-91cc-48efe71e4bda)

##### [ Decode, CPU menerjemahkan intruksi. bagian pertama adalah intruksi dan bagian kedua adalah lokasi. intruksinya adalah LOAD dan alamatnya adalah 6 jadi, kita akan memuat nilai di alamat 6 ke dalam akumulator ]
![2](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/35467dbb-9aa2-4a53-9d41-01987231a567)

##### [ Execute, CPU mengeksekusi instruksi ini dibutuhkan nilai di alamat 6 dan memuatnya ke akumulator. dalam hal ini nilainya adalah 1 ]
![3](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/f56b2864-5aea-4b30-b846-557b36fa6384)

##### [ Fetch, penghitung program bertambah dan CPU mengambil intruksi berikutnya di bit memori berikutnya ]
![4](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/f39429a6-3a42-41af-a40f-a0f3a478dc7c)

##### [ Decode, CPU menerjemahkan intruksi. kali ini ADD dan alamatnya 7, jadi di alamat 7 akan ditambahkan apa yang sudah ada di akumulator ]
![5](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/f55d478f-a9dc-4de6-816a-38a6f3bf356a)

##### [ Execute, CPU mengeksekusi interaksi lalu tambahkan nilainya di alamat 7. dalam hal ini, nilainya 1 jadi 1 + 1 = 2 ]
![6](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/87f9de7c-ae82-4699-9343-e86e0a85122b)

##### [ Fetch, dari lokasi memori berikutnya nomor 2 ]
![7](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/8c3f7d06-23be-4d59-b382-79c5bdd25d88)

##### [ Decode, intruksi untuk menyimpan nilai yang ada di akumulator ke dalam RAM di alamat 6 ]
![8](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/1d74c3e9-604a-4074-ba3c-d6061e50f811)

##### [ Execute, sekarang alamat 6 memiliki 2 di dalamnya bukan 1 ]
![9](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/3dd76b24-143a-4b90-ab17-2eb603a2db5e)

##### [ Fetch, intruksi baru JUMP (dengan lompatan) alamat berikutnya yang kita ambil adalah alamat yang ada di dalam instruksi ini ]
![10](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/b289c86c-5755-4c9c-9b86-4d122f803cdc)

##### [ Decode, lompat ke alamat nomor 1 ]
![11](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/358a18b0-93c9-49d8-b6c7-1d0ff6818465)

##### [ Execute, penghitung program kembali ke 1 ]
![12](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/c90247e9-4d41-4276-9a3e-090d7f7aa9fa)

#### Kemampuan untuk melompat, mengulang,  dan membuat instruksi adalah salah satu dasar ilmu komputer. jadi kembali ke atas, Fetch, Decode, lalu Execute program ini akan terus berulang hingga jumlahnya menjadi sangat besar sehingga bisa tidak lagi dipegang oleh alamat memori

# Tugas 3.3
#### Peran Bahasa Pemrograman : 
Bahasa pemrograman adalah cara bagi manusia untuk berkomunikasi dengan komputer. Memungkinkan programmer menulis kode dengan menggunakan struktur dan sintaks tertentu yang dapat dimengerti oleh komputer. Bahasa pemrograman menyediakan berbagai fitur dan abstraksi untuk memudahkan pengembangan perangkat lunak.

#### Peran Compiler : 
Compiler adalah perangkat lunak yang menerjemahkan kode sumber dalam bahasa pemrograman tingkat tinggi menjadi kode mesin yang dapat dimengerti oleh komputer. Compiler mengubah kode sumber menjadi bentuk yang dapat dieksekusi oleh CPU. Ini melibatkan proses analisis sintaksis, optimasi, dan pembuatan kode objek.

#### Peran Sistem Operasi : 
Sistem operasi (OS) bertindak sebagai perantara antara perangkat keras komputer dan perangkat lunak aplikasi. Mengelola sumber daya sistem seperti CPU, memori, dan perangkat input/output. Menyediakan antarmuka untuk berbagai fungsi sistem, termasuk manajemen file, multitasking, keamanan, dan jaringan. Sistem operasi memfasilitasi eksekusi program dengan mengatur alokasi sumber daya dan menjalankan proses secara efisien.

# Tugas 3.4
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
 
   
     







  




  
