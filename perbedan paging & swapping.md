## perbedaan paging dan swapping
- **Paging** merupakan kemungkinan solusi untuk permasalahan fragmentasi
eksternal dimana ruang alamat logika tidak berurutan; mengijinkan sebuah proses
dialokasikan pada memori fisik yang terakhir tersedia. Memori fisik dibagi ke dalam
blok-blok ukuran tetap yang disebut frame. Memori logika juga dibagi ke dalam blok-blok dg ukuran yang sama yang disebut page.
Pada skema paging, tidak terjadi fragmentasi eksternal, karena “sembarang”
frame dapat dialokasikan ke proses yang memerlukannya. Tetapi beberapa fragmentasi
internal masih mungkin terjadi. Hal ini dikarenakan frame dialokasikan sebagai unit
dan jika kebutuhan memori dari proses tidak menemukan page, maka frame terakhir
mungkin tidak dialokasikan penuh.
Bila suatu proses datang untuk dieksekusi, maka ukurannya diekspresikan
dengan page. Setiap page membutuhkan satu frame. Bila proses membutuhkan n
page, maka proses tersebut juga membutuhkan n frame. Jika tersedia n frame, maka
memori dialokasikan untuk proses tersebut. <br>
- **Swapping** merupakan Sebuah proses yang harus berada pada memori untuk dieksekusi. Proses juga dapat
ditukar (swap) sementara keluar memori ke backing store dan kemudian dibawa
kembali ke memori untuk melanjutkan eksekusi. Backing store berupa disk besar dengan kecepatan tinggi yang cukup untuk
meletakkan copy dari semua memory image untuk semua user, sistem juga harus
menyediakan akses langsung ke memory image tersebut. Contohnya, sebuah
lingkungan multiprogramming dengan penjadwalan CPU menggunakan algoritma
round-robin. Teknik swapping yang sudah dimodifikasi ditemui pada beberapa sistem
misalnya Linux, UNIX dan Windows. 
