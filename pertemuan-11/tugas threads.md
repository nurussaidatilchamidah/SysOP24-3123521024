# Tugas threads chapter 4 <br>
## **Practice Exercises** <br>
4.1 Provide three programming examples in which multithreading provides better performance than a single-threaded solution. <br>
*Answer:* <br>
a. A Web server that services each request in a separate thread. <br>
b. A parallelized application such as matrix multiplication where different parts of the matrix may be worked on in parallel. <br>
c. An interactive GUI program such as a debugger where a thread is used to monitor user input, another thread represents the running application, and a third thread monitors performance. <br>
*penjelasan soal 4.1 >>>* <br>
- Berikan tiga contoh pemrograman di mana multithreading memberikan kinerja yang lebih baik daripada solusi single-threaded. <br>
*Jawaban:* <br>
a. Server Web yang melayani setiap permintaan dalam thread terpisah. <br>
Multithreading memungkinkan server untuk menangani beberapa permintaan klien secara bersamaan, meningkatkan waktu respons dan pemanfaatan sumber daya dibandingkan dengan server single-threaded yang harus mengantri permintaan dan menanganinya satu per satu. <br>
b. Aplikasi terparallelisasi seperti perkalian matriks di mana bagian-bagian matriks dapat dikerjakan secara paralel. <br>
Multithreading dapat mendistribusikan komputasi elemen-elemen matriks ke beberapa thread, mempercepat keseluruhan komputasi dengan memanfaatkan banyak inti CPU. Setiap thread dapat bekerja pada segmen matriks yang berbeda, sehingga mengurangi waktu untuk menyelesaikan seluruh operasi. <br>
c. Program GUI interaktif seperti debugger di mana satu thread digunakan untuk memantau input pengguna, thread lain merepresentasikan aplikasi yang sedang berjalan, dan thread ketiga memantau kinerja. <br>
Multithreading memastikan bahwa antarmuka pengguna tetap responsif meskipun tugas-tugas lain sedang diproses. Satu thread dapat menangani interaksi pengguna, thread lain dapat menjalankan komputasi latar belakang, dan thread ketiga dapat memantau dan memperbarui metrik kinerja, memberikan pengalaman yang lancar dan interaktif. <br>

4.2 What are two differences between user-level threads and kernel-level threads? Under what circumstances is one type better than the other? <br>
*Answer:* <br>
a. User-level threads are unknown by the kernel, whereas the kernel is aware of kernel threads. <br>
b. On systems using either M:1 or M:N mapping, user threads are scheduled by the thread library and the kernel schedules kernel threads. <br>
c. Kernel threads need not be associated with a process whereas every user thread belongs to a process. Kernel threads are generally more expensive to maintain than user threads as they must be represented with a kernel data structure. <br>
*penjelasan soal 4.2 >>>* <br>
- Apa dua perbedaan antara thread tingkat pengguna dan thread tingkat kernel? Dalam keadaan apa salah satu jenis lebih baik daripada yang lain? <br>
*Jawaban:* <br>
a. Thread tingkat pengguna tidak diketahui oleh kernel, sedangkan kernel mengetahui keberadaan thread tingkat kernel. <br>
Thread tingkat pengguna dikelola oleh pustaka thread tingkat pengguna dan tidak terlihat oleh kernel. Kernel hanya mengetahui proses utama, bukan thread individual di dalamnya. Sebaliknya, thread tingkat kernel dikelola langsung oleh kernel sistem operasi, dan kernel sepenuhnya mengetahui serta dapat menjadwalkan thread-thread ini secara mandiri. <br>
b. Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna dijadwalkan oleh pustaka thread dan kernel menjadwalkan thread kernel. <br>
Pada pemetaan M:1 (many-to-one), banyak thread pengguna dipetakan ke satu thread kernel, dan pustaka thread tingkat pengguna bertanggung jawab untuk menjadwalkan thread-thread ini. Pada pemetaan M:N (many-to-many), banyak thread pengguna dipetakan ke banyak thread kernel, dan baik pustaka thread tingkat pengguna maupun kernel terlibat dalam penjadwalan. Thread kernel, bagaimanapun, dijadwalkan hanya oleh kernel. <br>
c. Thread kernel tidak harus terkait dengan suatu proses sedangkan setiap thread pengguna merupakan bagian dari proses. Thread kernel umumnya lebih mahal untuk dipelihara daripada thread pengguna karena harus diwakili dengan struktur data kernel. <br>
Thread kernel dapat eksis secara independen dari proses pengguna dan dikelola dengan struktur data tingkat kernel, yang membuatnya lebih memerlukan banyak sumber daya. Thread pengguna, di sisi lain, selalu merupakan bagian dari proses dan dikelola di dalam ruang pengguna, membuatnya lebih murah untuk dipelihara. <br>

4.3 Describe the actions taken by a kernel to context-switch between kernel-level threads. <br>
*Answer:* <br>
Context switching between kernel threads typically requires saving the value of the CPU registers from the thread being switched out and restoring the CPU registers of the new thread being scheduled. <br>
*penjelasan soal 4.3 >>>* <br>
- Jelaskan tindakan yang diambil oleh kernel untuk melakukan pergantian konteks antara thread tingkat kernel. <br>
*Jawaban:* <br>
Pergantian konteks antara thread kernel biasanya memerlukan penyimpanan nilai dari register CPU dari thread yang sedang dihentikan dan pemulihan register CPU dari thread baru yang dijadwalkan. Proses ini memungkinkan sistem operasi untuk secara efisien beralih antara thread yang berbeda, memanfaatkan CPU secara optimal dan memastikan bahwa semua thread mendapatkan waktu eksekusi yang diperlukan. <br>

4.4 What resources are used when a thread is created? How do they differ from those used when a process is created? <br>
*Answer:* <br>
Because a thread is smaller than a process, thread creation typically uses fewer resources than process creation. Creating a process requires allocating a process control block (PCB), a rather large data structure. The PCB includes a memory map, list of open files, and environment variables. Allocating and managing the memory map is typically the most time-consuming activity. Creating either a user or kernel thread involves allocating a small data structure to hold a register set, stack, and priority. <br>
*penjelasan soal 4.4 >>>* <br>
- Sumber daya apa yang digunakan ketika sebuah thread dibuat? Bagaimana mereka berbeda dari sumber daya yang digunakan ketika sebuah proses dibuat? <br>
*Jawaban:* <br>
Karena sebuah thread lebih kecil daripada sebuah proses, pembuatan thread biasanya menggunakan lebih sedikit sumber daya daripada pembuatan proses. Membuat sebuah proses memerlukan alokasi process control block (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file terbuka, dan variabel lingkungan. Alokasi dan pengelolaan peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat thread pengguna atau kernel melibatkan alokasi struktur data kecil untuk menyimpan set register, stack, dan prioritas. <br>

4.5 Assume that an operating system maps user-level threads to the kernel using the many-to-many model and that the mapping is done through LWPs. Furthermore, the system allows developers to create real-time threads for use in real-time systems. Is it necessary to bind a real-time thread to an LWP? Explain. <br>
*Answer:* <br>
Yes. Timing is crucial to real-time applications. If a thread is marked as real-time but is not bound to an LWP, the thread may have to wait to be attached to an LWP before running. Consider if a real-time thread is running (is attached to an LWP) and then proceeds to block (i.e., must perform I/O, has been preempted by a higher-priority real-time thread, is waiting for a mutual exclusion lock, etc.). While the real-time thread is blocked, the LWP it was attached to has been assigned to another thread. When the real-time thread has been scheduled to run again, it must first wait to be attached to an LWP. By binding an LWP to a real-time thread, you are ensuring the thread will be able to run with minimal delay once it is scheduled. <br>
*penjelasan soal 4.5 >>>* <br>
- Asumsikan bahwa sebuah sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model many-to-many dan pemetaan dilakukan melalui LWP. Selain itu, sistem memungkinkan pengembang untuk membuat thread real-time untuk digunakan dalam sistem real-time. Apakah perlu untuk mengikat sebuah thread real-time ke LWP? Jelaskan. <br>
*Jawaban:* <br>
Ya. Waktu sangat krusial untuk aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak diikat ke LWP, thread tersebut mungkin harus menunggu untuk dipasangkan dengan LWP sebelum berjalan. Pertimbangkan jika sebuah thread real-time sedang berjalan (terpasang ke LWP) dan kemudian terblokir (misalnya harus melakukan I/O, di-preempt oleh thread real-time dengan prioritas lebih tinggi, menunggu kunci eksklusi mutual, dll.). Ketika thread real-time terblokir, LWP yang terpasang padanya mungkin telah ditugaskan ke thread lain. Ketika thread real-time dijadwalkan untuk berjalan lagi, ia harus terlebih dahulu menunggu untuk dipasangkan dengan LWP. Dengan mengikat LWP ke thread real-time, Anda memastikan thread tersebut dapat berjalan dengan penundaan minimal begitu dijadwalkan. <br>

