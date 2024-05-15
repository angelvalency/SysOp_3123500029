<div align="center">
  <h1 style="font-weight: bold">TUGAS THREAD</h1>
  <h4 style="text-align: center;">Dosen Pengampu : Dr. Ferry Astika Saputra, S.T., M.Sc.</h4>
</div>
<br />
<br />
<div align="center">
  <img src="https://upload.wikimedia.org/wikipedia/id/4/44/Logo_PENS.png" alt="Logo PENS">
  <h3 style="text-align: center;">Disusun Oleh : </h3>
  <p style="text-align: center;">
    Firsty Angelica Valency (3123500029)<br>
  </p>
  <h3 style="text-align: center;line-height: 1.5">Program Studi Teknik Informatika<br>Departemen Teknik Informatika Dan Komputer<br>Politeknik Elektronika Negeri Surabaya<br>2023/2024</h3>
  <hr>
</div>


 Daftar Isi
<!-- - [Overview](#Overview) -->
- [Tugas Pendahuluan](#MultithreadingModels)
- [Daftar Pustaka](#Multicoreprogramming)

# Tugas Pendahuluan
1. Apa itu Thread ?
<br>
Jawab : 
<br>
 **Thread** adalah unit eksekusi yang merupakan bagian dari suatu proses. Suatu proses dapat memiliki banyak thread, semuanya dijalankan pada waktu yang sama. Ini adalah unit eksekusi dalam pemrograman bersamaan. 

2. Apa perbedaan dari Thread dan Proses?
<br>
jawab : 
<br>
Perbedaan antara **proses** dengan **thread** tunggal dengan proses dengan thread yang banyak (Multi thread) adalah proses dengan thread yang banyak dapat mengerjakan lebih dari satu tugas pada satu satuan waktu.

- Proses:

    - Sebuah proses adalah instance dari program yang sedang berjalan di sistem operasi.

    - Setiap proses memiliki alokasi memori yang terpisah, yang berarti data tidak langsung dapat diakses oleh proses lain tanpa pengaturan khusus seperti pertukaran pesan atau berbagi memori.

    - Proses biasanya lebih berat dalam hal overhead sistem karena mereka memiliki ruang memori terpisah dan sering memerlukan peralihan mode kernel ketika beralih dari satu proses ke proses lainnya.

    - Komunikasi antar proses (IPC) seringkali lebih rumit dan membutuhkan mekanisme khusus seperti shared memory, pipes, atau sockets.

- Thread:

    - Thread adalah unit terkecil dari eksekusi dalam sebuah proses. Satu proses dapat memiliki banyak thread.

    - Thread berbagi memori yang sama dalam konteks proses yang sama, yang membuat komunikasi antar thread lebih mudah dan lebih efisien.

    - Karena thread berbagi memori, mereka lebih ringan dalam hal overhead daripada proses. Peralihan antar thread jauh lebih cepat daripada peralihan antar proses.

    - Thread dapat berbagi sumber daya seperti variabel global, yang dapat menyebabkan masalah sinkronisasi jika tidak dikelola dengan benar. Sinkronisasi diperlukan untuk menghindari race condition dan deadlock.


3. Apa perbedaan utama antara thread dan proses dalam pemrograman konkurensi?
<br>
Jawab:
    - Thread adalah unit terkecil dari eksekusi dalam sebuah proses, sementara proses adalah instance dari program yang sedang berjalan di sistem operasi.

    - Thread berbagi memori yang sama dalam konteks proses yang sama, sementara setiap proses memiliki alokasi memori yang terpisah.

4. Bagaimana multithreading bisa memberikan kinerja yang lebih baik daripada solusi single-threaded?
<br>
Jawab:
    - Multithreading memungkinkan eksekusi beberapa tugas secara bersamaan, meningkatkan penggunaan sumber daya CPU dan mempercepat kinerja

    - aplikasi dalam situasi di mana beberapa tugas dapat dijalankan secara independen.

5. Apa perbedaan antara thread tingkat pengguna dan thread tingkat kernel?
<br>
Jawab:
    - Thread tingkat pengguna tidak dikenal oleh kernel, sementara kernel mengetahui thread tingkat kernel

    - Thread tingkat pengguna dijadwalkan oleh perpustakaan thread, sedangkan kernel menjadwalkan thread kernel.

6. Bagaimana proses pembuatan thread berbeda dengan pembuatan proses?
<br>
Jawab:
    - Thread biasanya membutuhkan lebih sedikit sumber daya dibandingkan proses karena ukuran yang lebih kecil.

    - Membuat proses memerlukan alokasi blok kontrol proses yang relatif besar, sementara membuat thread melibatkan alokasi struktur data yang lebih kecil.

7. Mengapa penting untuk mengikat thread real-time ke sebuah LWP dalam sistem operasi yang menggunakan model banyak-ke-banyak?
<br>
Jawab:
<br>
    Mengikat thread real-time ke sebuah LWP memastikan bahwa thread tersebut dapat berjalan dengan keterlambatan minimal setelah dijadwalkan, yang sangat penting dalam aplikasi real-time di mana waktu respons sangat krusial.

8. Berikut adalah tiga contoh pemrograman di mana penggunaan multithreading memberikan kinerja yang lebih baik daripada solusi single-threaded:
<br>
Jawab:
<br>
    a. Sebuah server web yang melayani setiap permintaan dalam thread terpisah.
    <br>
    b. Sebuah aplikasi yang diparalelisasi seperti perkalian matriks di mana bagian-bagian berbeda dari matriks dapat diolah secara paralel.
    <br>
    c. Sebuah program GUI interaktif seperti debugger di mana sebuah thread digunakan untuk memantau masukan pengguna, thread lain mewakili aplikasi yang sedang berjalan, dan thread ketiga memantau kinerja.

9. Berikut adalah dua perbedaan antara thread tingkat pengguna (user-level threads) dan thread tingkat kernel (kernel-level threads), serta situasi di mana satu tipe lebih baik daripada yang lain:
<br>
Jawab:
<br>
a. Thread tingkat pengguna tidak dikenal oleh kernel, sedangkan kernel mengetahui thread tingkat kernel.
<br>
b. Pada sistem yang menggunakan pemetaan M:1 atau M:N, thread pengguna dijadwalkan oleh perpustakaan thread sedangkan kernel menjadwalkan thread kernel.
<br>
c. Thread kernel tidak perlu terkait dengan proses sedangkan setiap thread pengguna milik sebuah proses. Thread kernel umumnya lebih mahal untuk dipelihara daripada thread pengguna karena harus direpresentasikan dengan struktur data kernel.

10.  Deskripsikan tindakan yang diambil oleh sebuah kernel untuk melakukan konteks-switching antara thread tingkat kernel:
<br>
Jawab:
<br>
Konteks-switching antara thread kernel biasanya memerlukan penyimpanan nilai register CPU dari thread yang akan diganti dan mengembalikan nilai register CPU dari thread yang baru dijadwalkan.

11. Sumber daya apa yang digunakan ketika sebuah thread dibuat? Bagaimana perbedaannya dengan sumber daya yang digunakan ketika sebuah proses dibuat?
<br>
Jawab:
<br>
    Karena sebuah thread lebih kecil dari sebuah proses, pembuatan thread biasanya menggunakan lebih sedikit sumber daya daripada pembuatan proses. Membuat sebuah proses memerlukan alokasi blok kontrol proses (PCB), sebuah struktur data yang cukup besar. PCB mencakup peta memori, daftar file terbuka, dan variabel lingkungan. Mengalokasikan dan mengelola peta memori biasanya merupakan aktivitas yang paling memakan waktu. Membuat sebuah thread pengguna atau kernel melibatkan alokasi struktur data kecil untuk menampung set register, tumpukan, dan prioritas.

12. Anggaplah bahwa sebuah sistem operasi memetakan thread tingkat pengguna ke kernel menggunakan model banyak-ke-banyak dan pemetaannya dilakukan melalui LWPs. Selain itu, sistem memungkinkan pengembang untuk membuat thread real-time untuk digunakan dalam sistem real-time. Apakah perlu mengikat sebuah thread real-time ke sebuah LWP? Jelaskan.
<br>
Jawab:
<br>
    Ya, penting. Waktu sangat penting dalam aplikasi real-time. Jika sebuah thread ditandai sebagai real-time tetapi tidak terikat ke sebuah LWP, thread tersebut mungkin harus menunggu untuk terpasang ke sebuah LWP sebelum berjalan. Pertimbangkan jika sebuah thread real-time sedang berjalan (terpasang ke sebuah LWP) dan kemudian terblokir (misalnya karena harus melakukan I/O, telah dipreempted oleh thread real-time dengan prioritas lebih tinggi, sedang menunggu kunci eksklusif bersama, dll.) Saat thread real-time tersebut diblokir, LWP yang terpasang kepadanya telah dialokasikan ke thread lain. Ketika thread real-time tersebut dijadwalkan untuk berjalan lagi, ia harus menunggu untuk terpasang ke sebuah LWP. Dengan mengikat sebuah LWP ke sebuah thread real-time, Anda memastikan thread tersebut akan dapat berjalan dengan keterlambatan minimal setelah dijadwalkan.

# Daftar Pustaka

- https://www.guru99.com/id/difference-between-process-and-thread.html

- https://blog.agungpambudi.com/2021/01/definisi-dan-perbedaan-antara-threads-dan-proses.html