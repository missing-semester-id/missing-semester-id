---
layout: lecture
title: "Mengapa kami mengajarkan hal ini"
# title: "Why we are teaching this class"
---

Selama perkuliahan tradisional dari bidang informatika, kamu pasti mengikuti
banyak kelas yang mengajarkan mu topik-topik lanjutan di bidang informatika,
mulai dari Sistem Operasi, Bahasa Pemrograman, sampai dengan Machine
Learning. Akan tetapi, dari sekian topik lanjutan tersebut, ada satu topik
penting yang jarang dibahas dan sebagai gantinya mahasiswa malah dibiarkan
untuk mempelajarinya sendiri: Literasi Ekosistem Komputer.
<!--
During a traditional Computer Science education, chances are you will take
plenty of classes that teach you advanced topics within CS, everything from
Operating Systems to Programming Languages to Machine Learning. But at many
institutions there is one essential topic that is rarely covered and is instead
left for students to pick up on their own: computing ecosystem literacy.
-->

Selama bertahun-tahun, kami telah mengajar di beberapa kelas di MIT,
dan sering sekali kami melihat banyaknya mahasiswa yang memiliki pengetahuan
yang sedikit tentang tools yang ada. Komputer dibuat untuk mengotomatiskan
pekerjaan yang bersifat manual, namun seringkali mahasiswa justru
melakukan pekerjaan manual yang repetitif tersebut ataupun tidak mengandalkan
tools yang ada seperti version control dan teks editor.Dalam skenario
terbaik pun, hal ini tetap membuang-buang waktu dan tidak efisien;
sedangkan untuk skenario terburuknya, hal seperti ini menghasilkan
masalah seperti kehilangan data ataupun ketidakmampuan untuk menyelesaikan
pekerjaan tertentu.
<!--
Over the years, we have helped teach several classes at MIT, and over and over
we have seen that many students have limited knowledge of the tools available
to them. Computers were built to automate manual tasks, yet students often
perform repetitive tasks by hand or fail to take full advantage of powerful
tools such as version control and text editors. In the best case, this results
in inefficiencies and wasted time; in the worst case, it results in issues like
data loss or inability to complete certain tasks.
-->

Topik-topik berikut ini tidak diajarkan di dalam kurikulum perkuliahan:
mahasiswa tidak pernah diajarkan untuk menggunakan tools ini, atau
setidaknya diajarkan cara yang efisien untuk menggunakannya, sehingga
membuang-buang waktu dan tenaga untuk pekerjaan yang _seharusnya_
sederhana. Kurikulum standar informatika tidak memiliki topik-topik
penting tentang ekosistem komputer yang secara signifikan bisa
mempermudah mahasiswa informatika.
<!--
These topics are not taught as part of the university curriculum: students are
never shown how to use these tools, or at least not how to use them
efficiently, and thus waste time and effort on tasks that _should_ be simple.
The standard CS curriculum is missing critical topics about the computing
ecosystem that could make students' lives significantly easier.
-->

# Semester yang hilang dari kuliah informatika
<!--
# The missing semester of your CS education
-->

Untuk memperbaiki hal ini, kami memberikan sebuah kelas pelajaran yang
mencakup semua topik-topik yang kami anggap krusial untuk menjadi
seorang computer scientist dan programmer yang efektif. Kelas ini
bersifat pragmatis dan praktis, dan menyediakan pengenalan terhadap
tools dan teknik yang kamu bisa langsung terapkan dalam berbagai
situasi dan kondisi yang akan kamu hadapi. Kelas ini dijalankan
selama "Periode Aktifitas Independen" di MIT pada bulan Januari tahun
2020 — semester berdurasi satu bulan yang berisikan kelas pendek
untuk para mahasiswa. Walaupun perkuliahannya sendiri hanya tersedia
untuk mahasiswa MIT, kami akan menyediakan semua materi perkuliahan
beserta rekaman video dari perkuliahan kepada publik.
<!--
To help remedy this, we are running a class that covers all the topics we
consider crucial to be an effective computer scientist and programmer. The
class is pragmatic and practical, and it provides hands-on introduction to
tools and techniques that you can immediately apply in a wide variety of
situations you will encounter. The class is being run during MIT's "Independent
Activities Period" in January 2020 — a one-month semester that features shorter
student-run classes. While the lectures themselves are only available to MIT
students, we will provide all lecture materials along with video recordings of
lectures to the public.
-->

Kalau ini dirasa cocok, berikut beberapa contoh dari apa yang akan
diajarkan di kelas:
<!--
If this sounds like it might be for you, here are some concrete
examples of what the class will teach:
-->

## Command shell

Bagaimana cara untuk mengotomatiskan pekerjaan yang umum dan repetitif
dengan alias, script, dan build system. Tidak ada lagi copy-paste
perintah dari dokumen teks. Tidak ada lagi "jalankan 15 perintah ini
satu per satu". Tidak adal lagi "kamu lupa menjalankan ini" ataupun
"kamu lupa untuk memasukkan argumen ini".
<!--
How to automate common and repetitive tasks with aliases, scripts,
and build systems. No more copy-pasting commands from a text
document. No more "run these 15 commands one after the other". No
more "you forgot to run this thing" or "you forgot to pass this
argument".
-->

Misalnya, pencarian melalui riwayat kamu secara cepat bisa menghemat waktu secara besar. Pada contoh berikut ini kami menunjukkan beberapa trik yang terkait dengan bernavigasi pada riwayat shell untuk perintah `convert`.
<!--
For example, searching through your history quickly can be a huge time saver. In the example below we show several tricks related to navigating your shell history for `convert` commands.
-->

<video autoplay="autoplay" loop="loop" controls muted playsinline  oncontextmenu="return false;"  preload="auto"  class="demo">
  <source src="/static/media/demos/history.mp4" type="video/mp4">
</video>

## Version control

Bagaimana cara menggunakan version control _dengan benar_, dan
memanfaatkannya untuk menyelamatkan mu dari bencana, berkolaborasi
dengan orang lain, dan secara cepat mencari dan memisahkan
perubahan yang bermasalah. Tidak ada lagi `rm -rf; git clone`.
Tidak ada lagi merge conflict (setidaknya lebih sedikit). Tidak
ada lagi blok komentar yang panjang pada code. Tidak ada lagi
kekhawatiran akan hal yang akan merusak code. Tidak ada lagi 
"oh tidak, apakah kita menghapus code yang sudah berfungsi ?!".
Kami bahkan akan mengajarkan kamu bagaimana caranya untuk
memberikan kontribusi terhadap proyek orang lain dengan pull request!
<!--
How to use version control _properly_, and take advantage of it to
save you from disaster, collaborate with others, and quickly find and
isolate problematic changes. No more `rm -rf; git clone`. No more
merge conflicts (well, fewer of them at least). No more huge blocks
of commented-out code. No more fretting over how to find what broke
your code. No more "oh no, did we delete the working code?!". We'll
even teach you how to contribute to other people's projects with pull
requests!
-->

Pada contoh berikut ini kita menggunakan `git bisect` untuk menemukan commit mana yang merusak unit test dan kemudian kita memperbaikinya dengan `git revert`.
<!--
In the example below we use `git bisect` to find which commit broke a unit test and then we fix it with `git revert`.
-->
<video autoplay="autoplay" loop="loop" controls muted playsinline  oncontextmenu="return false;"  preload="auto"  class="demo">
  <source src="/static/media/demos/git.mp4" type="video/mp4">
</video>

## Text editing

Bagaimana cara yang efisien untuk mengedit file dari command-line,
baik secara local maupun remote, dan memanfaatkan fitur lanjutan
dari text editor. Tidak ada lagi menyalin file kesana kemari.
Tidak ada lagi editing file yang repetitif.
<!--
How to efficiently edit files from the command-line, both locally and
remotely, and take advantage of advanced editor features. No more
copying files back and forth. No more repetitive file editing.
-->

Vim macro adalah salah satu fitur terbaik, pada contoh berikut kita secara cepat mengonversi sebuah html table menjadi format csv menggunakan nested vim macro.
<!--
Vim macros are one of its best features, in the example below we quickly convert an html table to csv format using a nested vim macro.
-->
<video autoplay="autoplay" loop="loop" controls muted playsinline  oncontextmenu="return false;"  preload="auto"  class="demo">
  <source src="/static/media/demos/vim.mp4" type="video/mp4">
</video>

## Remote machines

Bagaimana cara agar tetap segar saat bekerja pada remote machine
menggunakan SSH keys dan terminal multiplexing. Tidak ada lagi
membuka banyak terminal hanya untuk menjalankan dua perintah
secara bersamaan. Tidak ada lagi mengetik password setiap kali
akan melakukan koneksi. Tidak ada lagi kehilangan semuanya
hanya karena Internet kamu putus ataupun kamu harus reboot
laptop kamu.
<!--
How to stay sane when working with remote machines using SSH keys and
terminal multiplexing. No more keeping many terminals open just to
run two commands at once. No more typing your password every time you
connect. No more losing everything just because your Internet
disconnected or you had to reboot your laptop.
-->

Pada contoh berikut ini kita menggunakan `tmux` untuk menjaga sesi tetap hidup di remote server dan `mosh` untuk mendukung network roaming dan disconnection.
<!--
In the example below we use `tmux` to keep sessions alive in remote servers and `mosh` to support network roaming and disconnection.
-->

<video autoplay="autoplay" loop="loop" controls muted playsinline  oncontextmenu="return false;"  preload="auto"  class="demo">
  <source src="/static/media/demos/ssh.mp4" type="video/mp4">
</video>

## Pencarian file
<!--
## Finding files
-->

Bagaimana cara cepat untuk mencari file yang kamu butuhkan.
Tidak ada lagi mengklik melalui file di dalam proyek kamu
sampai kamu menemukan code yang kamu inginkan.
<!--
How to quickly find files that you are looking for. No
more clicking through files in your project until you find the one
that has the code you want.
-->

Pada contoh berikut kita secara cepat mencari file dengan `fd`
dan untuk code snippets dengan `rg`. Kita juga secara cepat `cd`
dan `vim` file atau folder yang terbaru atau sering dibuka
menggunakan `fasd`.
<!--
In the example below we quickly look for files with `fd` and for code snippets with `rg`. We also quickly `cd` and `vim` recent/frequent files/folder using `fasd`.
-->

<video autoplay="autoplay" loop="loop" controls muted playsinline  oncontextmenu="return false;"  preload="auto"  class="demo">
  <source src="/static/media/demos/find.mp4" type="video/mp4">
</video>

## Perselisihan data
<!--
## Data wrangling
-->

Bagaimana cara cepat dan mudah untuk mengubah, melihat, parse,
plot, dan mengkomputasi data dan file langsung dari command-line.
Tidak ada lagi copy-paste dari log file. Tidak ada lagi komputasi
statistik yang manual dari data. Tidak ada lagi spreadsheet plotting.
<!--
How to quickly and easily modify, view, parse, plot, and compute over
data and files directly from the command-line. No more copy pasting
from log files. No more manually computing statistics over data. No
more spreadsheet plotting.
-->

## Mesin virtual
<!--
## Virtual machines
-->

Bagaimana cara menggunakan mesin virtual untuk mencoba sistem
operasi yang baru, mengisolasi proyek yang tidak berhubungan,
dan menjaga mesin utama kamu bersih dan rapi. Tidak ada lagi
merusak komputer mu secara tidak sengaja selama melakukan
security lab. Tidak ada lagi jutaan paket acak yang terinstall
dengan versi yang berbeda-beda.
<!--
How to use virtual machines to try out new operating systems, isolate
unrelated projects, and keep your main machine clean and tidy. No
more accidentally corrupting your computer while doing a security
lab. No more millions of randomly installed packages with differing
versions.
-->

## Keamanan
<!--
## Security
-->

Bagaimana caranya berselancar di Internet tanpa langsung
mengungkapkan semua rahasia kamu kepada dunia. Tidak ada lagi
password yang harus berisikan kriteria gila. Tidak ada lagi
jaringan WiFi terbuka yang tidak aman. Tidak ada lagi
perpesanan yang tidak terenkripsi.

<!--
How to be on the Internet without immediately revealing all of your
secrets to the world. No more coming up with passwords that match the
insane criteria yourself. No more unsecured, open WiFi networks. No
more unencrypted messaging.
-->

# Kesimpulan
<!--
# Conclusion
-->

Contoh-contoh tersebut, dan masih banyak lagi, akan dibahas
di 12 kelas perkuliahan, masing-masing termasuk latihan untuk
kamu supaya kamu semakin terbiasa dengan tools tersebut.
Kalau kamu tidak bisa menunggu sampai bulan Januari, kamu
juga bisa melihat-lihat perkuliahan dari [Hacker Tools]
(https://hacker-tools.github.io/lectures/), yang mana kami
jalankan selama IAP tahun lalu. Itu adalah pendahulu dari
kelas ini, dan mencakup banyak topik yang sama.
<!--
This, and more, will be covered across the 12 class lectures, each including an
exercise for you to get more familiar with the tools on your own. If you can't
wait for January, you can also take a look at the lectures from [Hacker
Tools](https://hacker-tools.github.io/lectures/), which we ran during IAP last
year. It is the precursor to this class, and covers many of the same topics.
-->

Kami berharap bisa bertemu dengan mu di bulan Januari,
baik secara virtual maupun langsung!
<!--
We hope to see you in January, whether virtually or in person!
-->

Happy hacking,<br>
Anish, Jose, and Jon
