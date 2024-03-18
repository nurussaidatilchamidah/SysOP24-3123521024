# TUGAS 4
## Operasi Input Output

### TUGAS PENDAHULUAN:
**Jawablah pertanyaan-pertanyaan di bawah ini :**
1. Apa yang dimaksud redirection? <br>
Pembelokan (redirection) dilakukan untuk standard input, output dan error, yaitu untuk mengalihkan file descriptor dari 0, 1 dan 2. <br>
2. Apa yang dimaksud pipeline? <br>
Mekanisme pipa digunakan sebagai alat komunikasi antar proses. <br>
3. Apa yang dimaksud perintah di bawah ini : _echo, cat, more, sort, grep, wc, cut, uniq_
  - Echo : untuk menampilkan output kelayar.
  - Cat : untuk menghasilkan output kelayar dan merupakan berasal dari input sebuah keyboard.
  - More : perintah untuk mempaging halaman.
  - Sort : untuk mengurutkan masukannya berdasarkan urutan nomor ASCII dari karakter.
  - Grep : untuk menyaring masukannya da n menampilkan baris-baris yang hanya mengandung pola yang ditentukan. Pola ini disebut regular expression
  - Wc : untuk menghitung jumlah baris, kata dan karakter dari baris-baris masukan yang diberikan kepadanya.
  - Cut : untuk mengambil kolom tertentu dari baris-baris masukannya, yang ditentukan pada option –c.
  - Uniq : untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, biasanya digabungkan dalam pipeline dengan sort


### PERCOBAAN:
1. Login sebagai user.
2. Bukalah Console Terminal dan lakukan percobaan-percobaan di bawah ini. Perhatikan hasil setiap percobaan.
3. Selesaikan soal-soal latihan.

### Percobaan 1 : File descriptor
1. Output ke layar (standar output), input dari system (kernel)
```
$ ps
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/8e543557-af9f-47bb-9387-e8ce34af72a7)
<br> Analisa :  menunjukkan bahwa proses identify 3454 dan 3460 dengan totaly 0 pada cmd bash dan ps

2. Output ke layar (standar output), input dari keyboard (standard input)
```
 $ cat
 hallo, apa khabar
 hallo, apa khabar
 exit dengan ^d
 exit dengan ^d
 [Ctrl-d]
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/badcda13-554b-460c-94ae-b988162d739a)
<br> Analisa : contoh penulisan standar dari keyboard untuk mengakhiri inputan dengan menekan tombol ctrl + d maka akan otomotis kembali ke path root

3. Input nama direktori, output tidak ada (membuat direktori baru), bila terjadi error maka tampilan error pada layar (standard error)
```
$ mkdir mydir
$ mkdir mydir **(Terdapat pesan error)**
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/f62272a5-a1db-4c78-bd52-9bc9285058a0)
<br> Muncul pesan berupa mkdir : cannot create directory ‘mydir’ : file exists maksud pesan tersebut yaitu direktori yang hendak dibuat “mydir” sudah ada/sudah dibuat. Sehingga ketika perintah mkdir perintah tersebut di tolak/ tidak dapat dilakukan.

