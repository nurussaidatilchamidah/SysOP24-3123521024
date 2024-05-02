# TUGAS 5 (pertemuan ke-8)
## hubungan arsitektur CPU dengan arsitektur OS <br>
Arsitektur CPU dan arsitektur sistem operasi (OS) saling berhubungan erat karena keduanya berperan penting dalam 
menjalankan aplikasi dan memproses instruksi-instruksi komputer. Berikut adalah beberapa aspek hubungan antara keduanya : <br>
a. *Instruksi dan Perintah* : Arsitektur CPU menentukan instruksi-instruksi dasar yang dapat dieksekusi oleh CPU. 
Sistem operasi harus memahami arsitektur CPU tersebut untuk mengirimkan instruksi-instruksi kepada CPU dan memastikan bahwa aplikasi dapat berjalan dengan benar. <br>
b. *Interaksi Hardware* : CPU berinteraksi langsung dengan perangkat keras (hardware) dalam komputer, seperti memori dan perangkat masukan/keluaran. 
Sistem operasi bertugas untuk mengelola interaksi ini dengan memastikan alokasi sumber daya yang efisien dan pengaturan penggunaan perangkat keras yang optimal. <br>
c. *Optimasi Kinerja* : Sistem operasi sering kali melakukan optimasi kinerja yang spesifik untuk arsitektur CPU tertentu. Hal ini bisa meliputi pengaturan penjadwalan proses, 
manajemen memori, dan strategi akses perangkat keras yang dioptimalkan untuk karakteristik arsitektur CPU yang digunakan. <br>
Dengan demikian, arsitektur CPU dan arsitektur sistem operasi sangat terkait satu sama lain dalam menjalankan aplikasi dan mengelola sumber daya komputer secara efisien.
Perubahan dalam salah satu arsitektur dapat mempengaruhi cara sistem operasi beroperasi, dan sebaliknya.

## perbedaan CISC dan RISC <br>
perbedaan *CISC (Complex Instruction Set Computing) dan RISC (Reduced Instruction Set Computing)* secara sederhananya adalah <br>
- CISC : memiliki komponen sedikit dan instruksi program banyak atau lebih complex <br>
- RISC : memiliki komponen banyak dan instruksi program sedikit atau lebih sederhana <br>

## Fork : Parent - Child Process <br>
- Akses dan clonning repo : https://github.com/ferryastika/operatingsystem.git <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/d6d4d93f-a8cc-405f-8203-2cd2d1b00a75)
<br> **masuk ke root lalu akses dan clonning repo. setelah itu melihat direktori dan masuk ke direktori operatingsystem** <br>
- Install gcc g++ <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/1aa37fa1-c580-4f9b-92e5-67809b890b76)
<br> **sebelum menjalankan fork, install gcc g++ terlebih dahulu** <br>
- fork01.c <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/5f84911b-5f46-4dc7-b1c9-25265205a2ec)
<br> **hasil diatas menunjukkan bahwa proses saat ini diidentifikasi oleh ID Process (PID) dan User ID (UID). pada baris pertama
terjadi child process lalu baris kedua parent process dan baris ketiga owner process. program diatas berulang sebanyak 3 kali** <br>
- fork02.c <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/310db255-913a-4cbe-835a-79b3c0c59030)
<br> **hasil diatas menunjukkan proses yang berjalan bersamaan di dalam Debian, termasuk variabel X, dan ID unik dari masing-masing proses tersebut** <br>
- fork03.c <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/46e97953-4102-4e98-9893-2f8433552510)
<br> **hasil diatas menunjukkan proses yang sedang berjalan serta ID unik dari masing-masing proses tersebut** <br> 
- orphan.c <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/f29bdd0f-57ef-4a2d-8e7f-1c3db6f13136)
<br> **Orphan Process adalah sebuah proses yang ada dalam komputer dimana parent process telah selesai aatu berhenti bekerja
namun proses anak (child process) sendiri tetap berjalan.** <br>
- zombie.c <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/7fcbdc3e-8f89-4748-8de1-35b776c11591)
<br> **Zombie Process terjadi karena adaanya child process yang di exit namun parrent processnya tidak tahu bahwa child process tersebut telah di terminate. Sehingga parent process tidak merelease process yang masih digunakan oleh child process tersebut walaupun process tersebut sudah mati.**




