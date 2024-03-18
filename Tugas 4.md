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

### Percobaan 2 : Pembelokan (redirection)
1. Pembelokan standar output
```
 $ cat 1> myfile.txt
 Ini adalah teks yang saya simpan ke file myfile.txt
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/821f19be-0d6a-411e-96f1-87b6a80bccc3)
<br> Analisa : Membuat file baru dengan nama myfile dengan ekstensi txt, isi file di inputkan oleh keyboard yaitu “ini adalah teks yang saya simpan ke file myfile.txt”

2. Pembelokan standar input, yaitu input dibelokkan dari keyboard menjadi dari file
 ```
 $ cat 0< myfile.txt
 $ cat myfile.txt
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/18640121-540c-4591-bdc3-57ca02349f88)
<br> Analisa : Perintah cat myfile.txt ialah perintah untuk menampilkan isi file yang telah dibuat

3. Pembelokan standar error untuk disimpan di file
 ```
 $ mkdir mydir (Terdapat pesan error)
 $ mkdir mydir 2> myerror.txt
 $ cat myerror.txt
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/0562ab7e-f1a1-4c2e-a023-4258e98f678c)
<br> Analisa :  menggunakan perintah mkdir mydir 2> merupakan metode pembelokan standar error untuk kemudian disimpan di file

4. Notasi 2>&1 : pembelokan standar error (2>) adalah identik dengan file descriptor 1.
 ```
 $ ls filebaru (Terdapat pesan error)
 $ ls filebaru 2> out.txt
 $ cat out.txt
 $ ls filebaru 2> out.txt 2>&
 $ cat out.txt
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/40b7ed53-10a3-4ea6-afe0-5f7e6eb61b53)
<br> Analisa : dengan menggunakan perintah (2>) maka akan terjadi pembelokan standar error adalah identik dengan file descriptor 1.

5. Notasi 1>&2 (atau >&2) : pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error
```
$ echo “mencoba menulis file” 1> baru
$ cat filebaru 2> baru 1>&
$ cat baru
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/79e27d3c-a150-461f-a028-70b2158c7a5d)
<br> Analisa : dengan menggunakan perintah echo serta notasi 1 dan 2 maka akan melakukan pembelokan standar output adalah sama dengan file descriptor 2 yaitu standar error

6. Notasi >> (append)
```
$ echo “kata pertama” > surat
$ echo “kata kedua” >> surat
$ echo “kata ketiga” >> surat
$ cat surat
$ echo “kata keempat” > surat
$ cat surat
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/71458867-de85-4391-8e76-5637e7daad70)
<br> Analisa : Notasi >> (append) digunakan untuk membelokkan tampilan standard output ke file tanpa menghapus isi dari file sebelumnya

7. Notasi here document (<<++ .... ++) digunakan sebagai pembatas input dari keyboard. Perhatikan bahwa tanda pembatas dapat digantikan dengan tanda apa saja, namun harus sama dan tanda penutup harus diberikan pada awal baris
```
$ cat <<++
Hallo, apa kabar?
Baik-baik saja?
Ok!
++
$ cat <<%%%
Hallo, apa kabar?
Baik-baik saja?
Ok!
%%%
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/053b9472-9e75-441c-8465-3097c1feea3e)
<br> analisa : dengan menggunakan perintah <<++ dapat digunakan sebagai pembatas input dari keyboard namun harus sama dan tanda penutup harus diberikan pada awal baris.

8. Notasi – (input keyboard) adalah representan input dari keyboard. Artinya menampilkan file 1, kemudian menampilkan input dari keyboard dan menampilkan file 2. Perhatikan bahwa notasi “-“ berarti menyelipkan input dari keyboard
```
$cat myfile.txt – surat
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/130d2b5b-0e66-4647-87c0-c25f53446d21)
<br> Analisa : dengan menggunakan perintah (-) lalu akan menampilkan input dari keyboard dan menampilkan file 2

### Percobaan 3 : Pipa (pipeline)
1. Operator pipa (|) digunakan untuk membuat eksekusi proses dengan melewati data langsung ke data lainnya.
```
$ who
$ who | sort
$ who | sort –r
$ who > tmp
$ sort tmp
$ rm tmp
$ ls –l /etc | more
$ ls –l /etc | sort | more
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/2a16bb22-d67a-4209-92c8-5ea9cd92f968)
<br> Analisa : menggunakan perintah Operator pipa ( | ) berfungsi membuat eksekusi proses dengan melewati data langsung ke data lainnya.

2. Untuk membelokkan standart output ke file, digunakan operator ">"
```
$ echo hello
$ echo hello > output
$ cat output
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/94c37b07-5c3c-476a-ba93-cba3aa6ff95f)
<br> Analisa : perintah untuk membelokkan standart output ke file menggunakan operator > 

3. Untuk menambahkan output ke file digunakan operator ">>"
```
$ echo bye >> output
$ cat output
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/55f3f830-45cc-49c4-9fa8-5d0cc279f69a)
<br> Analisa : Untuk menambahkan output ke file digunakan operator >>

4. Untuk membelokkan standart input digunakan operator "<"
```
$ cat < output
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/4db2c9de-7c0f-4ede-a924-200fae673722)
<br> Analisa : Untuk membelokkan standar input ke file digunakan operator >>

5. Pembelokan standart input dan standart output dapat dikombinasikan tetapi tidak boleh menggunakan nama file yang sama sebagai standart input dan output.
```
$ cat < output > out
$ cat out
$ cat < output >> out
$ cat out
$ cat < output > output
$ cat output
$ cat < out >> out (Proses tidak berhenti)
[Ctrl-c]
$ cat out
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/9f2fcd49-2187-472e-a578-659f78e241b0)
<br> Analisa : dengan menggunakan kombinasi standar input dan standar output lalu akan melakukan pembelokan namun nama file tidak boleh sama sebagai standar input dan output


### Percobaan 4 : Filter
1. Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks
 ```
 $ w –h | grep <user>
 $ grep <user> /etc/passwd
 $ ls /etc | wc
 $ ls /etc | wc –l
 $ cat > kelas1.txt
 Badu
 Zulkifli
 Yulizir
 Yudi
 Ade
 [Ctrl-d]
 $ cat > kelas2.txt
 Budi
 Gama
 Asep
 Muchlis
 [Ctrl-d]
 $ cat kelas1.txt kelas2.txt | sort
 $ cat kelas1.txt kelas2.txt > kelas.txt
 $ cat kelas.txt | sort | uniq
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/d25fa117-ad4b-46ef-9456-ccf1714a2c86)
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/ef081ad6-f533-466e-ab20-ec8e960eee8f)
<br> Analisa : selain itu  operator Pipa juga digunakan untuk mengkombinasikan utilitas sistem untuk membentuk fungsi yang lebih kompleks

### LATIHAN :
1. Lihat daftar secara lengkap pada direktori aktif, belokkan tampilan standard output ke file baru. <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/e669afa3-e211-405d-9367-a75511fd4a69)
<br> analisa : Untuk melihat daftar direktori aktif, gunakan perintah $ ls, sedangkan untuk membelokkan tampilan standard output ke file baru, gunakan “>”

2. Lihat daftar secara lengkap pada direktori /etc/passwd, belokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya. <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/ec35ee93-4bf7-4bf9-ae41-68d11576695f)
<br> analisa : Untuk melihat daftar lengkap dari direktori /etc/passwd, gunakan perntah $ ls, sedangkan untuk membelokkan tampilan standard output ke file baru tanpa menghapus file baru sebelumnya, gunakan ‘>>’

3. Urutkan file baru dengan cara membelokkan standard input. <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/9257c761-9e96-4de1-8faa-dd9b741b2ae4)
<br> analisa : Untuk mengurutkan file, gunakan perintah $ sort, sedangkan untuk membelokkan standard input, gunakan ‘<’

4. Urutkan file baru dengan cara membelokkan standard input dan standard output ke file baru.urut. <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/0b9a2ee9-0241-420f-a977-b800d29e3608)
<br> analisa : Untuk mengurutkan file, gunakan perintah $ sort, sedangkan untuk membelokkan standard input, gunakan ‘’. Pembelokan standart input dan standart output dapat dikombinasikan asalkan tidak boleh menggunakan nama file yang sama sebagai standart input dan output

5. Buatlah direktori latihan 2 sebanyak 2 kali dan belokkan standard error ke file rmdirerror.txt.
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/08fc4351-6e25-4875-8363-d068deeedc91)
<br> analisa : Gunakan perintah $ mkdir untuk membuat direktori baru. Saat membuat direktori yang sama sebanyak dua kali, akan muncul pesan error. Pesan error itu kemudian dibelokkan ke file dengan menggunakan ‘2>’

6. Urutkan kalimat berikut :
```
Jakarta
Bandung
Surabaya
Padang
Palembang
Lampung
```
Dengan menggunakan notasi here document (<@@@ ...@@@) . HINT <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/c787758c-a106-4945-bdcd-c56e33ac7e67)
<br> analisa : Pertama, buat notasi here document yang akan dibelokkan ke sebuah file kemudian isi document tersebut. Setelah diisi dan diakhiri, isi dokumen akan tersimpan ke file yang dibelokkan. File tersebut kemudian diurutkan menggunakan perintah $ sort

7. Hitung jumlah baris, kata dan karakter dari file baru.urut dengan menggunakan filter dan tambahkan data tersebut ke file baru. <br>
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/982a4439-c514-48cc-9189-95837691960b)
<br> analisa : Untuk mendapatkan jumlah baris, kata, dan karakter (secara berurutan) dari sebuah file, gunakan perintah wc yang dipipakan dengan perintah cat. Hasilnya kemudian bisa ditambahkan ke file menggunakan ‘>>’

8. Gunakan perintah di bawah ini dan perhatikan hasilnya.
```
 $ cat > hello.txt
 dog cat
 cat duck
 dog chicken
 chicken duck
 chicken cat
 dog duck
 [Ctrl-d]
 $ cat hello.txt | sort | uniq
 $ cat hello.txt | grep “dog” | grep –v “cat”
```
![image](https://github.com/nurussaidatilchamidah/SysOP24-3123521024/assets/160559227/bada6026-0c4c-4556-a1a2-7b76cddaa920)
<br> analisa : Uniq digunakan untuk menghilangkan baris-baris berurutan yang mengalami duplikasi, Grep digunakan untuk menyaring masukannya dan menampilkan baris-baris yang hanya mengandung pola yang ditentukan. 
