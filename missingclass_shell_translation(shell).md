---
layout: lecture
title: "Gambaran Kursus + the shell"
date: 2020-01-13
ready: true
video:
  aspect: 56.25
  id: Z56Jmr9Z34Q
---

# Motivasi

Sebagai ilmuwan komputer, kita tahu bahwa komputer sangat baik dalam membantu kita dalam mengerjakan tugas-tugas yang repetitif. Namun, terlalu sering kita lupa bahwa hal ini berlaku juga pada proses kita dalam menggunakan komputer itu sendiri, prinsip yang sama berjalan saat program-program yang kita buat menjalankan komputasi yang kita inginkan.  
Kita memiliki pelbagai alat tersedia di ujung jari kita yang memungkinkan kita untuk menjadi lebih produktif dan membantu kita menyelesaikan masalah lain yang lebih kompleks dalam pelbagai aspek yang terkait dengan komputer. Namun, banyak dari kita hanya menggunakan sebagian kecil dari alat-alat tersebut; kita hanya tahu beberapa "mantra ajaib" secara hafalan untuk bisa melewati suatu proses dan dengan buta menyalin serta menempelkan  
perintah dari internet saat kita mengalami kesulitan.

Kelas ini merupakan jawaban untuk mengatasi hal tersebut.

Kami ingin memandu Anda bagaimana memanfaatkan alat-alat yang telah Anda ketahui,  menunjukkan alat-alat baru untuk ditambahkan ke kotak perkakas Anda, dan  menanamkan kegembiraan pada Anda untuk bereksplorasi (serta mungkin membangun) lebih banyak alat sendiri. Ini adalah apa yang kita yakini sebagai semester yang terluput dari sebagian besar kurikulum kampus jurusan ilmu Komputer.

# Struktur Kelas

Kuliah ini terdiri dari 11 kelas yang masing-masing berdurasi selama 1 jam, setiap kelas tersebut  
berfokus pada suatu [topik tertentu](/2020/). Kelas-kelas tersebut sebagian besar  
berdiri sendiri(tanpa terkait dengan materi kelas lainnya), meskipun seiring berjalannya semester, kita akan menganggap  
bahwa Anda sudah familiar dengan konten dari kelas-kelas sebelumnya. Kami  
mempunyai catatan tertlusi dari kelas online, tetapi ada banyak konten yang dibahas di  
rekaman video (misalnya dalam bentuk demo) yang mungkin tidak ada di catatan tersebut.  
Kami akan merekam kelas-kelas yang ada dan mempublikasikan hasilnya secara online.

Kami berusaha untuk mancakup sebanyak mungkin materi, sehingga pada akhirnya kelas-kelas tersebut cukup padat. Untuk memberi Anda waktu  
untuk menguasai materi dengan kecepatan yang diinginkan, setiap kelas  
terdiri dari serangkaian latihan yang membimbing Anda melalui poin-poin kunci  
kelas tersebut. Setelah setiap kelas selesai , kita akan mengadakan jam konsultasi  
di mana kita akan membantu menjawab pertanyaan apa pun yang  
mungkin Anda miliki. Jika Anda mengikuti kelas secara online, Anda dapat  
mengirimkan pertanyaan kepada kita melalui  
[missing-semester@mit.edu](mailto:missing-semester@mit.edu).

Dikarenakan waktu yang terbatas, kita tidak dapat mencakup semua alat dengan  
tingkat detail yang sama sepert suatu kelas penuh. Jika memungkinkan, kita akan  
mencoba menunjukkan Anda ke sumber-sumber belajar lain yang lebih mendalam, tetapi jika ada sesuatu yang membuat Anda tertarik, jangan ragu untuk menghubungi kita dan meminta petunjuk!

# Topik 1: Shell

## Apa itu shell?

Komputer saat ini memiliki pelbagai antarmuka untuk memudahkan kita dalam memberikan perintah  
kepadanya; antarmuka pengguna grafis yang indah, antarmuka suara, dan  
bahkan AR/VR ada di mana-mana. Ini bagus untuk 80% kasus penggunaan,  
tetapi seringkali mereka tidak memberika keleluasaan lebih kepada anda — Semisal anda tidak dapat menekan tombol atau memberikan perintah suara yang belum diprogram. Untuk benar-benar memanfaatkan  
alat-alat yang disediakan komputer, kita harus kembali ke antarmuka teks: Shell.

Hampir semua platform yang dapat Anda temui memiliki sebuah shell dalam suatu bentuk dan beragam varian lainnya. Meskipun mereka mungkin bervariasi dalam beberapa hal, pada intinya semua kurang lebih sama: mereka memungkinkan Anda menjalankan program, mengirimkan input, dan memeriksa output dengan cara yang semi-terstruktur.

Dalam kelas ini, kita akan fokus pada Bourne Again SHell, atau "bash" untuk  
singkatnya. Ini merupakan salah satu shell yang paling banyak digunakan, dan  
sintaksnya mirip dengan yang akan Anda lihat di banyak shell lain. Untuk membuka  
_prompt_ shell (di mana Anda dapat mengetik perintah), Anda pertama kali  
memerlukan *terminal*. 

Perangkat Anda mungkin sudah dilengkapi dengan salah satu variasi shell tersebut atau kalau belum, Anda dapat menginstalnya dengan cukup mudah.

## Menggunakan shell

Ketika Anda meluncurkan terminal, Anda akan melihat _prompt_ yang seringkali  
terlihat seperti ini:

```console
missing:~$ 
```

Ini adalah antarmuka teks utama pada shell. Ini memberi tahu Anda bahwa Anda
sedang memakai sebuah komputer yang bernama `missing` dan bahwa "direktori kerja saat ini" atau tempat
Anda berada saat ini adalah `~` (singkatan untuk "home"). Tanda `$` dapat diartikan bahwa Anda bukan pengguna root (akan dibahas secara lebih detail nanti). Pada prompt ini, Anda dapat mengetikkan _command_ yang kemudian akan coba dipahami oleh shell. Perintah yang paling dasar adalah menjalankan program:

```console
missing:~$ date
Fri 10 Jan 2020 11:49:31 AM EST
missing:~$ 
```

Di sini, kita telah menjalankan program `date`, yang mungkin tidak akan  mengejutkan bahwa ia akan mencetak tanggal dan waktu saat ini. Shell kemudian meminta kita untuk perintahlain yang akan dijalankan. Kita juga dapat menjalankan perintah dengan argumen:

```console
missing:~$ echo hello
hello
```

Dalam kasus ini, kita memberi tahu shell untuk menjalankan program `echo` dengan
argumen `hello`. Program `echo` hanya akan  mencetak output argumennya. Shell menguraikan
perintah dengan membaginya berdasarkan spasi, dan kemudian menjalankan program yang
ditunjukkan oleh kata pertama, menyediakan setiap kata berikutnya sebagai argumen
yang dapat diakses oleh program. Jika Anda ingin memberikan argumen yang berisi
spasi atau karakter khusus lainnya (mis., direktori bernama "My Photos"), Anda
dapat mengutip argumen tersebut dengan tanda `'` atau `"` (`"My Photos"`), atau berikan jeda antara kata dengan `\` (`My\ Photos`).

Namun, bagaimana shell tahu cara menemukan program-program seperti `date` atau `echo`?
Nah, shell merupakan sebuah lingkungan pemrograman, sama seperti Python atau Ruby, sehingga ia
memiliki variabel, kondisional, loop, dan fungsi (akan dibahas pada kelas berikutnya). Ketika Anda menjalankan perintah di shell, Anda sebenarnya menulis potongan kode kecil
yang akan diinterpretasikan oleh shell. Jika shell diminta untuk menjalankan perintah
yang tidak cocok dengan salah satu kata kunci pemrograman miliknya (syntax), ia akan memeriksa sebuah variabel lingkungan yang bernama `$PATH` yang berisi direktori-direktori yang harus dicari shell untuk menemukan program-program yang diperintahkan untuk dicari:

```console
missing:~$ echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
missing:~$ which echo
/bin/echo
missing:~$ /bin/echo $PATH
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

Ketika kita menjalankan perintah `echo`, shell melihat bahwa ia harus menjalankan
program `echo` dan kemudian mencari melalui daftar direktori yang dipisahkan oleh
: di `$PATH` untuk file dengan nama tersebut. Ketika ia menemukannya, ia akan menjalankannya (dengan asumsi bahwa file tersebut dapat eksekusi; lebih lanjut tentang ini akan dibahas nanti). Kita dapat mengetahui file mana yang dijalankan untuk suatu nama program tertentu menggunakan program `which`. Kita juga dapat mengabaikan `$PATH` sepenuhnya dengan memberikan path ke file yang ingin kita jalankan.

## Navigasi di shell
Sebuah path di shell adalah daftar terbatas direktori-direktori yand ada di komputer; dipisahkan oleh `/` di Linux dan macOS dan `\` di Windows. Pada Linux dan macOS, path `/` adalah "root" dari sistem file, semua direktori dan file berada di bawahnya, sedangkan di Windows ada satu root untuk setiap partisi disk (misal `C:\`). Kami akan mengasumsikan bahwa pada umumnya Anda menggunakan sistem file Linux dalam kelas ini. Sebuah path yang dimulai dengan `/` disebut path absolute. Path lainnya adalah path relatif. Path
relatif maksudnya adalah relatif terhadap direktori kerja saat ini, yang dapat kita lihat dengan perintah `pwd` dan ubah dengan perintah `cd`. Dalam sebuah path, . merujuk pada direktori sekarang, dan `..` pada direktori induknya:

```console

missing:~$ pwd
/home/missing
missing:~$ cd /home
missing:/home$ pwd
/home
missing:/home$ cd ..
missing:/$ pwd
/
missing:/$ cd ./home
missing:/home$ pwd
/home
missing:/home$ cd missing
missing:~$ pwd
/home/missing
missing:~$ ../../bin/echo hello
hello
```

Perhatikan bahwa prompt shell kita terus memberi tahu kita tentang direktori kerja
saat ini kita. Anda dapat mengonfigurasi prompt Anda untuk menunjukkan pelbagai
informasi yang berguna, yang akan kita bahas dalam kelas berikutnya.

Secara umum, ketika kita menjalankan suatu program, ia akan beroperasi di direktori
kerja saat ini kecuali diberitahu sebaliknya. Misalnya, itu biasanya akan mencari
file di sana, dan membuat file baru di sana jika diperlukan.

Untuk melihat apa yang ada di direktori tertentu, kita menggunakan perintah `ls`:

```console
missing:~$ ls
missing:~$ cd ..
missing:/home$ ls
missing
missing:/home$ cd ..
missing:/$ ls
bin
boot
dev
etc
home
...
```

Kecuali sebuah direktori diberikan sebagai argumen pertamanya, `ls` akan mencetak
isi dari direktori kerja saat ini. Sebagian besar perintah menerima bendera dan
pilihan (bendera dengan nilai) yang dimulai dengan `-` untuk memodifikasi perilaku
mereka. Biasanya, menjalankan program dengan bendera `-h` atau `--help` akan
mencetak teks bantuan yang memberi tahu Anda bendera dan opsi apa yang tersedia.
Misalnya, `ls --help` memberi tahu kita:

```
  -l                         gunakan format daftar panjang
```

```console

missing:~$ ls -l /home
drwxr-xr-x 1 missing  users  4096 Jun 15  2019 missing
```

Ini memberi kita banyak informasi tambahan tentang setiap file atau direktori
yang ada. Pertama, `d` di awal baris memberi tahu kita bahwa `missing` adalah
sebuah direktori. Adapun tiga kelompok dari tiga karakter (`rwx`), ini
menunjukkan izin apa yang dimiliki pemilik file (`missing`), grup para pemilik (`users`),
dan semua orang lain pada item terkait. - menunjukkan bahwa pemegang hak tidak
memiliki izin tertentu. Di atas, hanya pemilik yang diizinkan untuk mengubah (`w`)
direktori `missing` (yaitu, menambahkan/menghapus file di dalamnya). Untuk masuk
ke direktori, pengguna harus memiliki izin "search" (direpresentasikan oleh "eksekusi":
`x`) pada direktori tersebut (dan induknya). Untuk mencetak isi, pengguna harus
mempunyai izin baca (`r`) pada direktori tersebut. Untuk file, izinnya seperti yang
Anda biasanya bayangkan. Perhatikan bahwa hampir semua file di `/bin` memiliki izin `x` yang diatur untuk kelompok terakhir, "semua orang lain", sehingga siapa pun dapat menjalankan program-program itu.

Beberapa program bermanfaat lainnya yang perlu diketahui pada saat ini adalah `mv` (untuk mengganti/memindahkan file), `cp` (untuk menyalin file), dan `mkdir` (untuk membuat direktori baru).

Jika Anda ingin mendapatkan informasi lebih lanjut tentang argumen, masukan, keluaran, atau cara kerja umum suatu program, coba gunakan program `man`. Program ini mengambil nama program sebagai argumen dan menampilkan halaman panduan untuk program tersebut. Tekan `q` untuk keluar.

```console

missing:~$ man ls
```

## Menghubungkan program

Dalam shell, program memiliki dua "aliran" utama yang terkait dengan mereka: aliran masuk dan aliran keluar. Ketika program mencoba membaca masukan, ia membaca dari aliran masukan, dan ketika mencetak sesuatu, ia mencetak ke aliran keluaran. Biasanya, masukan dan keluaran program adalah terminal Anda. Yaitu keyboard Anda sebagai media masukan dan layar Anda sebagai media keluaran. Namun, kita juga dapat mengalihkan aliran-aliran tersebut!

Bentuk paling sederhana dari pengalihan adalah `< file` dan `> file`. Ini memungkinkan Anda mengalihkan aliran masukan dan keluaran suatu program ke filenya masing-masing:

```console
missing:~$ echo hello > hello.txt
missing:~$ cat hello.txt
hello
missing:~$ cat < hello.txt
hello
missing:~$ cat < hello.txt > hello2.txt
missing:~$ cat hello2.txt
hello
```

Seperti yang ditunjukkan pada contoh di atas, `cat` adalah program yang menggabungkan berkas (concatenate). Ketika diberikan nama berkas sebagai argumen, ia mencetak isi setiap berkas secara berurutan ke aliran keluarannya. Namun, ketika `cat` tidak diberikan argumen, ia mencetak konten dari aliran masuk ke aliran keluar (seperti pada contoh ketiga di atas).

Anda juga dapat menggunakan `>>` untuk menambahkan sesuatu ke berkas. Keadaan dimana jenis pengalihan masukan/keluaran ini benar-benar berguna adalah dalam penggunaan pipe. Operator `|` memungkinkan Anda "menghubungkan" program sehingga keluaran satu program menjadi masukan program lain:

```console
missing:~$ ls -l / | tail -n1
drwxr-xr-x 1 root  root  4096 Jun 20  2019 var
missing:~$ curl --head --silent google.com | grep --ignore-case content-length | cut --delimiter=' ' -f2
219
```

Selanjutnya, kita akan membahas lebih detail bagaimana memanfaatkan pipe dalam kelas tentang pengelolaan data.

# Alat yang serbaguna dan kuat

Pada sebagian besar sistem yang mirip dengan Unix, ada seorang pengguna yang diistimewakan: pengguna "root". Anda mungkin telah melihatnya dalam daftar berkas di atas. Pengguna root berada di atas (hampir) semua batasan akses, dan dapat membuat, membaca, memperbarui, dan menghapus berkas apa pun dalam sistem. Namun, biasanya Anda tidak akan masuk ke sistem Anda sebagai pengguna root, karena bisa jadi ada implikasi untuk terlalu mudah dalam merusak sesuatu secara tidak sengaja. Sebagai antisipasinya, Anda akan menggunakan perintah `sudo`. Sesuai namanya, perintah ini memungkinkan Anda "melakukan" sesuatu "sebagai su" (singkatan dari "super user" atau "root"). Ketika Anda mendapatkan pesan kesalahan yang berbentuk Permission denied, hal itu berarti bahwa Anda perlu melakukan sesuatu sebagai root. Meskipun demikian, pastikan terlebih dahulu bahwa Anda benar-benar ingin melakukannya dengan cara itu!

Satu hal yang perlu Anda lakukan sebagai root adalah menulis ke sistem berkas sysfs yang dipasang pada `/sys`. `sysfs` mengekspos sejumlah parameter kernel sebagai berkas, sehingga Anda dapat dengan mudah mengkonfigurasi kernel secara langsung tanpa peralatan khusus. **Perhatikan, sysfs tidak ada di Windows atau macOS.**

Sebagai contoh, kecerahan layar laptop Anda diekspos melalui berkas bernama `brightness` pada

```
/sys/class/backlight
```

Dengan menulis nilai ke berkas tersebut, kita dapat mengubah kecerahan layar. Insting pertama Anda mungkin seperti ini:

```console
$ sudo find -L /sys/class/backlight -maxdepth 2 -name '*brightness*'
/sys/class/backlight/thinkpad_screen/brightness
$ cd /sys/class/backlight/thinkpad_screen
$ sudo echo 3 > brightness
An error occurred while redirecting file 'brightness'
open: Permission denied
```

Kesalahan ini mungkin mengejutkan. Bagaimanapun, kita menjalankan perintah dengan menggunakan `sudo`! Ini adalah hal penting yang perlu diketahui tentang shell. Operasi seperti `|`, `>`, dan `<` dilakukan oleh shell, bukan oleh program individu. `echo` dan kawan-kawannya tidak "tahu" tentang |. Mereka hanya membaca dari masukan mereka dan menulis ke keluaran mereka, apa pun itu. Dalam kasus di atas, _shell_ (yang diotentikasi untuk anda sebagai pengguna) mencoba membuka berkas kecerahan untuk penulisan sebelum menetapkannya sebagai keluaran sudo `echo`, tetapi dicegah karena shell tidak berjalan sebagai root. Dengan pengetahuan ini, kita dapat mengatasinya dengan:

```console
$ echo 3 | sudo tee brightness
```

Karena program `tee` yang membuka berkas `/sys` untuk penulisan, dan itu dijalankan sebagai `root`, semua izin dapat berfungsi. Anda bisa mengontrol pelbagai hal yang menyenangkan dan berguna melalui `/sys`, seperti status LED sistem yang berbeda (jalur Anda mungkin berbeda):

```console
$ echo 1 | sudo tee /sys/class/leds/input6::scrolllock/brightness
```

# Langkah selanjutnya

Pada saat ini, Anda sudah cukup mengenal shell untuk menyelesaikan tugas-tugas dasar. Anda seharusnya dapat menjelajah untuk menemukan berkas-berkas yang menarik dan menggunakan fungsionalitas dasar dari kebanyakan program. Pada kelas berikutnya, kita akan membahas cara melakukan dan mengotomatisasi tugas-tugas yang lebih kompleks menggunakan shell dan banyak program baris perintah yang berguna di luar sana.

# Latihan

Semua kelas dalam kursus ini disertai dengan serangkaian latihan. Beberapanya berisi tugas spesifik untuk dilakukan, sementara yang lain bersifat umum, seperti "coba gunakan program X dan Y". Kami sangat mendorong Anda untuk mencobanya.

Kami tidak menulis solusi untuk latihan-latihan tersebut. Jika Anda terhambat pada sesuatu, silakan kirimkan email yang menjelaskan apa yang sudah Anda coba kepada kami, dan kami akan mencoba membantu Anda.


  1. Untuk kursus ini, Anda perlu menggunakan shell Unix seperti Bash atau ZSH. Jika Anda menggunakan Linux atau macOS, Anda tidak perlu melakukan instalasi/persiapan khusus apa pun. Jika Anda menggunakan Windows, pastikan Anda tidak menjalankan cmd.exe atau PowerShell; Anda dapat menggunakan [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/) atau mesin virtual Linux untuk menggunakan alat baris perintah gaya Unix. Untuk memastikan bahwa Anda menggunakan shell yang tepat, coba tulis perintah `echo $SHELL`. Jika itu menghasilkan sesuatu seperti `/bin/bash` atau `/usr/bin/zsh`, itu berarti Anda menjalankan program yang benar.
  2. Buat direktori baru bernama missing di bawah /tmp.
  3. Cari program `touch`. Program `man` adalah teman Anda.
  4. Gunakan `touch` untuk membuat berkas baru bernama `semester` di dalam `missing`.
  5. Tuliskan hal berikut ke dalam berkas tersebut, satu baris pada satu waktu:

      ```
      #!/bin/sh
      curl --head --silent https://missing.csail.mit.edu
      ```

      Baris pertama mungkin sulit untuk dijalankan. Penting untuk diketahui bahwa `#` digunakan untuk memulai sebuah komentar dalam Bash, dan `!` memiliki makna khusus bahkan dalam string berpetik ganda (`"`). Bash memperlakukan string berpetik tunggal (`` `) secara berbeda: mereka akan berhasil dalam hal ini. Lihat halaman manual Bash tentang quoting untuk informasi lebih lanjut. [quoting](https://www.gnu.org/software/bash/manual/html_node/Quoting.html)
  6. Coba jalankan berkas tersebut, yaitu ketik jalur ke skrip (`./semester`) ke dalam shell Anda dan tekan enter. Pahami mengapa ini tidak berfungsi dengan memeriksa output dari `ls` (petunjuk: lihatlah bit izin berkas).
  7. Jalankan perintah dengan secara eksplisit memulai interpreter `sh`, dan memberikan berkas semester sebagai argumen pertama, yaitu `sh` semester. Mengapa ini berhasil, sedangkan ./semester tidak?
  8. Cari `chmod` (misalnya, gunakan man chmod).
  9. Gunakan chmod untuk memungkinkan jalankan perintah ./semester daripada harus mengetik `sh` semester. Bagaimana shell Anda tahu bahwa berkas tersebut seharusnya diinterpretasikan menggunakan `sh`? Lihat halaman [shebang](https://en.wikipedia.org/wiki/Shebang_(Unix)) untuk informasi lebih lanjut.
  10. Gunakan `|` dan `>` untuk menuliskan output "terakhir diubah" yang dihasilkan oleh `semester` ke dalam berkas bernama `last-modified.txt` di direktori home Anda.
  11. Tulis sebuah perintah yang dapat membaca tingkat daya baterai laptop atau suhu CPU mesin desktop Anda dari `/sys`. Catatan: jika Anda pengguna macOS, OS Anda tidak memiliki sysfs, jadi Anda dapat melewati latihan ini.

