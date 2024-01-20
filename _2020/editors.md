---
layout: lecture
title: "Editors (Vim)"
date: 2020-01-15
ready: true
video:
  aspect: 56.25
  id: a6Q8Na575qc
---

Penulisan dokumen atau artikel dalam bahasa natural sangat berbeda dengan 
penulisan kode program. Saat menulis kode program, biasanya seorang programmer 
menghabiskan waktu lebih untuk berpindah antar file, membaca file yang berbeda, 
dan mengubah isi file-file tersebut dibanding fokus pada satu file dalam waktu 
yang lama seperti penulisan dokumen bahasa natural. Sehingga, cukup masuk akal 
jika program komputer yang digunakan dalam menulis bahasa natural berbeda dengan 
untuk menulis kode program (contohnya _Microsoft Word versus Visual Studio Code_).

Sebagai seorang _programmer_, kita menghabiskan banyak waktu dalam menulis dan 
mengedit kode program. Sehingga, penguasaan _editor_ yang cocok dengan kebutuhan 
kita sangatlah berguna untuk menambah produktifitas kerja kita. Untuk belajar 
_editor_ baru, biasanya, _programmer_ dapat melakukan langkah-langkah berikut:

- Mulai dengan mempelajari suatu tutorial (contoh. kuliah ini, dan sumber-sumber
materi yang terdapat pada dokumen ini)
- Fokus menggunakan _editor_ yang ingin dipelajari untuk keperluan sehari-hari
(Meskipun hal ini akan membuat pekerjaan menjadi agak lambat di awal penggunaan
editor)
- Mencari trik-trik baru dalam penggunaan _editor_ sesuai dengan kebutuhan anda
sebagai _programmer_

Jika anda mengikuti metode diatas, dan selalu menggunakan _editor_ yang sedang 
dipelajari dalam tiap pekerjaan anda, perjalanan belajar anda akan seperti 
berikut: Dalam satu atau dua jam, anda akan mempelajari fungsi dasar _editor_ 
seperti, membuka dan mengedit _file_, menyimpan perubahan/keluar aplikasi, dan 
navigasi _buffer_. Sesudah 20 jam, anda harusnya sudah sangat nyaman seperti 
menggunakan  _editor_ yang biasa anda gunakan sebelumnya. Setelah itu, keunggulan 
menggunakan editor baru ini akan terasa: anda akan memiliki pengetahuan dan hapal 
di luar kepala dalam menggunakan _editor_ ini sehingga banyak waktu yang dapat 
dihemat. _Editor_ teks modern merupakan _tools_ yang cukup _powerful_, dalam 
perjalanan  menggunakan _editor_ ini, anda akan menemukan trik-trik baru yang 
membuat pekerjaan anda semakin cepat dan efisien!

# Editor apakah yang akan dipelajari?

_Programmer_ memiliki [opini yang kuat](https://id.wikipedia.org/wiki/Perang_editor) 
tentang _editor_ teks terbaik versi mereka. 

Untuk melihat editor mana yang populer sekarang, anda bisa melihat 
[survey _Stack Oveflow_](https://insights.stackoverflow.com/survey/2019/#development-environments-and-tools)
(mungkin terdapat bias pada survey ini, karena pengguna _Stack Overflow_
tidak merepresentasikan komunitas programmer secara menyeluruh). [_Visual Studio
Code_](https://code.visualstudio.com/) adalah _editor_ terpopuler dalam survey 
tersebut. Dan [Vim](https://www.vim.org/) adalah _editor_ berbasis _command line_
yang paling populer.

## Vim
Semua pengajar dalam kelas ini menggunakan _Vim_ sebagai editor. Sejarah _Vim_  
cukup panjang. _Vim_ dikembangkan dari editor _Vi_ (1976), yang sampai sekarang
pun masih dikembangkan. _Vim_ memiliki banyak fungsionalitas yang berguna, karena
alasan ini, banyak _tools_ yang memiliki _support_ emulasi _Vim_ (contohnya, 1.4 
juta orang telah menginstall [Vim emulation untuk VS code](https://github.com/VSCodeVim/Vim)).
Karena alasan tersebut, _Vim_ mungkin tetap sangat berguna untuk dipelajari, meskipun 
pada akhirnya anda memilih untuk menggunakan _editor_ lain.

# Filosofi _Vim_

Ketika menulis kode program, anda akan menggunakan lebih banyak waktu anda untuk 
membaca dan mengedit, bukan menulis dalam waktu panjang pada satu file. Oleh sebab 
itu, Vim adalah editor _modal_: ia memiliki berbagai macam _mode_ untuk memyisipkan 
dan memanipulasi teks. _Vim_ adalah editor yang _programmable_ (menggunakan 
_Vimscript_ dan bahasa pemrograman lain seperti _Python_), dan antarmuka _Vim_ 
sendiri adalah bahasa pemrograman: tiap tombol keyboard (dengan penamaan yang 
mudah diingat) merupakan perintah operasi, dan perintah operasi ini dapat digabungkan 
sesuai kebutuhan. _Vim_ menghindari penggunaan mouse, karena dapat memperlambat 
proses kerja kita. Selain mouse, _Vim_ juga menghindari penggunaan tombol arah, 
karena penggunaannya dapat memperlambat navigasi dalam file. 

# Modal editing

Design _Vim_ berdasarkan argumen bahwa banyak waktu _programmer_ dihabiskan untuk
membaca, menavigasi, dan melakukan perubahan dalam skala kecil pada file-file basis 
kode yang dikerjakan. Hal tersebut berbeda dengan penulisan teks yang banyak dan 
cenderung fokus pada satu file seperti pada penulisan dokumen atau artikel bahasa 
natural. Karena alasan tersebut, Vim memiliki beberapa mode operasi.

- **Normal**: untuk navigasi dalam file dan melakukan perubahan pada teks dalam file
- **Insert**: untuk menyisipkan teks
- **Replace**: untuk me-replace teks
- **Visual** (plain, line, atau block): untuk memilih blok teks
- **Command-line**: untuk menjalankan perintah

Tiap tombol memiliki kegunaan yang berbeda dalam mode operasi yang berbeda. 
Contohnya, tombol huruf `x` dalam mode Insert berfungsi untuk menyisipkan huruf 
'x' seperti layaknya dalam teks editor umum. Namun, dalam mode Normal, tombol 
huruf `x` berfungsi untuk menghapus huruf dalam kursor aktif. Lain pula dalam mode 
Visual, tombol tersebut akan menghapus teks yang terseleksi.

Dalam pengaturan defaultnya, _Vim_ menampilkan mode yang aktif di bagian kiri bawah.
Mode awal/default dalam _Vim_ adalah mode Normal. Saat menggunakan _Vim_, anda akan 
banyak menghabiskan waktu pada mode Normal dan mode Insert.

Kita dapat mengaktifkan atau kembali ke mode Normal dari mode lain dengan 
menekan `<ESC>` (tombol escape). Dari mode Normal, kita bisa menekan tombol `i` 
untuk mengaktifkan mode Insert, tombol `R` untuk mode Replace, tombol `v` untuk mode
Visual, `V` untuk mode Visual Line, `<C-v>` (Ctrl-V, kadang ditulis juga dengan `^V`)
untuk Visual mode Visual Block, dan tombol `:` untuk mode Command-line. 

Kita akan menggunakan tombol `<ESC>` cukup sering ketika menggunakan _Vim_: salah 
satu tips agar jangkauannya menjadi lebih dekat, adalah dengan melakukan _remapping_
Caps Lock ke tombol Escape ([instruksi untuk pengguna 
macOS](https://vim.fandom.com/wiki/Map_caps_lock_to_escape_in_macOS)).

# Dasar-dasar Vim

## Menyisipkan teks

Dalam mode Normal, tekan `i` untuk masuk kedalam mode Insert. Dalam mode ini,
Vim bekerja seperti teks editor pada umumnya. Untuk kembali ke mode Normal, 
kita dapat menekan tombol `<ESC>`. Mengetahui dua hal ini cukup untuk memulai 
menggunakan _Vim_ (Namun hal ini akan sangat tidak efisien, terutama karena kita
menghabiskan waktu kita untuk melakukan editing dalam mode Insert).

## Buffer, tab, dan window

"Buffer" adalah file-file yang sedang di tangani/dibuka oleh _Vim_. Suatu sesi 
_Vim_ biasanya memiliki beberapa tab, dimana tiap tabnya memilki beberapa window. 
Setiap window menampilkan sebuah buffer. Berbeda dengan program komputer yang 
biasa kita pakai (contohnya browser web), buffer dan window tidak memilki hubungan 
satu satu (1-to-1); windows hanya berfungsi sebagai view (menampilkan buffer).
Satu buffer dapat dibuka dengan lebih dari satu window, meski dalam satu tab 
yang sama. Hal ini sangat berguna, contohnya ketika kita ingin melihat bagian
berbeda dalam satu file secara bersamaan. 

Dalam kondisi default, _Vim_ akan terbuka dengan satu tab yang berisi satu
window.

## Mode command-line

Kita dapat masuk kedalam mode command-line dengan cara menekan tombol `:` pada 
mode Normal. Kursor akan berpindah ke baris perintah saat tombol `:` ditekan. Mode
ini memiliki banyak kegunaan, seperti membuka, menyimpan dan menutup file. Dan
tak lupa untuk [menutup _Vim_](https://twitter.com/iamdevloper/status/435555976687923200).

- `:q` keluar ('quit', menutup window)
- `:w` simpan ('write')
- `:wq` simpan dan keluar
- `:e {nama file}` buka file untuk editing
- `:ls` menampilkan buffer-buffer yang terbuka
- `:help {topik}` membuka panduan _Vim_
    - `:help :w` membuka panduan untuk perintah `:w`
    - `:help w` membuka panduan untuk tombol `w`

# Antarmuka _Vim_ sebagai bahasa pemrograman

Salah satu hal terpenting dalam _Vim_ adalah antarmuka _Vim_ sendiri merupakan
sebuah bahasa pemrograman. Tombol keyboard (dengan penamaan yang mudah diingat) 
adalah perintah, dan perintah-perintah ini dapat digabungkan satu sama lain. 
Hal tersebut dapat menambah efisiensi dalam pergerakan dan penyuntingan teks 
atau kode program. Terutama saat pengguna hapal diluar kepala akan perintah-perintah
yang ada. 

## Perpindahan
Biasanya saat menggunakan _Vim_, waktu kita akan banyak digunakan untuk berpindah
dalam dan antar buffer pada mode Normal, menggunakan perintah-perintah perpindahan.
Perpindahan dalam _Vim_ disebut juga dengan "nouns", karena perintah-perintahnya 
merujuk pada potongan teks.

- Perintah perpindahan dasar: `hjkl` (kiri, bawah, atas, kanan)
- Kata: `w` ('word', kata selanjutnya), `b` ('beginning', awal dari kata), 
`e` ('end', akhir dari kata)
- Baris: `0` (awal baris), `^` (karakter _non-blank_ pertama), `$` (akhir baris)
- Layar: `H` (atas layar), `M` (tengah layar), `L` (bawah layar)
- _Scroll_: `Ctrl-u` (atas), `Ctrl-d` (bawah)
- File: `gg` (awal dari file), `G` (akhir dari file)
- Nomor baris: `:{nomor}<CR>` atau `{nomor}G` (baris {nomor})
- Pasangan: `%` (berpindah ke karakter pasangan, misal untuk tanda kurung kiri 
dan kanan)
- Temukan: `f{karakter}`, `t{karakter}`, `F{karakter}`, `T{karakter}`
    - temukan/ke kedepan/kebelakang {karakter} pada baris aktif 
    - `,` / `;` untuk berpindah ke {karakter} yang cocok
- Pencarian: `/{regex}`, `n` / `N` untuk berpindah ke item yang cocok

## Seleksi

Mode visual:

- Visual: `v`
- Visual line: `V`
- Visual Block: `Ctrl-v`

Dengan menggunakan mode ini kita dapat menggunakan tombol gerak untuk menyeleksi 
teks secara visual. 

## Edit 

Pekerjaan yang biasanya bisa kita kerjakan menggunakan mouse, dapat kita kerjakan
menggunakan keyboard dengan perintah editing, digabungkan dengan perintah pergerakan.
Dengan melakukan hal tersebut, antarmuka _Vim_ mulai mirip dengan bahasa pemrograman.
Perintah editing dalam _Vim_ dikenal juga dengan "verbs", karena (dalam bahasa 
inggris) verbs bertindak pada nouns.

- `i` masuk keadalam mode Insert
    - namun, untuk memanipulasi/menghapus teks, kita ingin menggunakan cara lain 
    selain menggunakan tombol backspace
- `o` / `O` sisipkan baris baru di bawah/atas kursor aktif
- `d{pergerakan}` menghapus (delete) {pergerakan}
    - Contoh: `dw` digunakan untuk menghapus kata (word), `d$` hapus sampai akhir 
    baris, `d0` hapus sampai awal baris
- `c{pergerakan}` ubah {pergerakan}
    - Contoh `cw` digunakan untuk menghubah kata
    - Seperti `d{pergerakan}` diikuti dengan `i`
- `x` hapus satu karakter/huruf (sepadan dengan `d1`)
- `s` ganti karakter/huruf (sepadan dengan `xi`)
- Mode Visual + manipulasi 
    - seleksi teks yang diinginkan, `d` untuk menghapus atau `c` untuk mengubah 
- `u` untuk membatalkan perubahan terakhir (undo), `C-r` untuk redo
- `y` untuk menyalin (copy) / "yank" (beberapa perintah lain seperti `d` juga menyalin)
- `p` untuk menyisipkan item yang telah disalin (paste)
- Banyak perintah lain juga untuk dipelajari: contoh `-` untuk membalik _case_ 
sebuah huruf.

## Hitungan (Counts)

Kita dapat mengkombinasikan nouns dan verbs dengan counts. Dengan enggunakan counts,
perintah kita akan dilakukan sebanyak sekian kali.

- `3w` berpindah 3 huruf kedepan
- `5j` berpindah 3 baris kebawah
- `7dw` hapus 7 huruf

## Modifiers

Kita dapat menggunakan modifiers untuk mengubah "arti" dari sebuah noun. 
Salah satu modifiers yang sering digunakan adalah `i`, yang artinya "inner"
atau "inside" (di dalam). Kemudian`a`, yang artinya "around" (sekitar).

- `ci(` ubah konten di dalam tanda kurung ()
- `ci[` ubah konten didalam tanda kurung []
- `da'` hapus string tanda petik satu `'`, termasuk string di sekitarnya

# Contoh kasus

Mari kita lihat contoh penggalan program [fizz buzz](https://en.wikipedia.org/wiki/Fizz_buzz)
yang masih perlu diperbaiki agar implementasinya benar:

```python
def fizz_buzz(limit):
    for i in range(limit):
        if i % 3 == 0:
            print('fizz')
        if i % 5 == 0:
            print('fizz')
        if i % 3 and i % 5:
            print(i)

def main():
    fizz_buzz(10)
```

Kita akan memperbaiki beberapa masalah dibawah ini

- Fungsi `main()` belum dipanggil 
- Perulangan dimulai dengan angka 0 (harusnya 1)
- "fizz" dan "buzz" tidak tercetak pada baris berbeda untuk kelipatan 15
- Kelipatan 5 memunculkan "fizz" 
- Penggunaan argumen angka 10 yang _hard-coded_ alih-alih menggunakan argumen 
command-line 

{% comment %}
- fungsi `main()` belum dipanggil
  - `G` pergi ke bagian akhir file
  - `o` membuat baris baru
  - sisipkan "if __name__ ..." 
- perulangan dimulai dengan angka 0 (harusnya 1)
  - cari kata "range" dengan perintah `/range`
  - `ww` untuk maju 2 kata
  - `i` untuk menyisipkan teks "1, " 
  - `ea` untuk menyisipkan "+1" setelah variabel `limit`
- buat baris baru untuk "fizzbuzz"
  - `jj$i` untuk menyisipkan teks pada akhir baris
  - tambahkan ", end=''"
  - `jj.` ulangi untuk perintah print kedua
  - `jjo` buat baris baru dibawah if
  - tambahkan "else: print()"
- fizz fizz
  - `ci'` untuk mengganti fizz
- argumen command-line 
  - `ggO` untuk membuka baris pertama dan akhir baris
  - "import sys"
  - `/10`
  - `ci(` sisipkan "int(sys.argv[1])"
{% endcomment %}

Tonton video perkuliahan untuk demonstrasi langsung langkah-langkah diatas.
Coba bandingkan bagaimana jika kita menggunakan editor lain untuk melakukan
pekerjaan yang sama. Kita bisa melihat bahwa dengan menggunakan _Vim_, proses
edit bisa dilakukan dengan lebih cepat karena kita menekan tombol keyboard 
dalam frekuensi yang lebih sedikit. 

# Pengaturan _Vim_

Agar _Vim_ cocok sesuai kebutuhan dan preferensi kita, kita dapat mengubah
pengaturan _Vim_ melalui file '~/.vimrc' (yang berisi perintah perintah _Vimscript_).
Mungkin ada beberapa pengaturan yang ingin kita aktifkan untuk mempermudah 
pekerjaan kita.

Tutorial ini menyediakan konfigurasi dasar yang terdokumentasi dengan baik
untuk digunakan sebagai file konfigurasi awal kita. Kami merekomendasikan
untuk memakai konfigurasi ini, agar beberapa hal yang kurang praktis dari 
pengaturan default _Vim_ bisa dihindari.  **Silahkan unduh konfigurasi
tersebut [disini](/2020/files/vimrc) dan simpan ke dalam `~/.vimrc`.**

Pengaturan _Vim_ sangatlah kaya dan fleksibel. Mempelajari berbagai macam
opsi pengaturan dalam _Vim_ sangatlah direkomendasikan. Anda dapat melihat 
_ditfiles_ pengguna _Vim_ lain di GitHub sebagai referensi untuk konfigurasi 
anda. Sebagai contoh, konfigurasi _Vim_ pengajar turorial ini dapat dilihat di:  
([Anish](https://github.com/anishathalye/dotfiles/blob/master/vimrc),
[Jon](https://github.com/jonhoo/configs/blob/master/editor/.config/nvim/init.vim) 
(uses [neovim](https://neovim.io/)), [Jose](https://github.com/JJGO/dotfiles/blob/master/vim/.vimrc)). 
Selain referensi diatas, banyak juga postingan blog bagus yang membahas topik ini.
Cobalah untuk tidak hanya melakukan _copy-paste_ konfigurasi pengguna _Vim_
lain, namun baca, pahami, dan ambil bagian-bagian yang anda butuhkan.

# Menambah kapabilitas _Vim_

Banyak sekali _plugin_ yang dapat digunakan untuk menambah kapabilitas _Vim_.
Berbeda dengan saran yang mungkin bisa kita temukan di internet, anda _tidak_
diharuskan untuk menggunakan manajemen _plugin_ untuk _Vim_ (sejak versi 8.0).
Karena _Vim_ sudah memiliki sistem manajemen _plugin_ nya sendiri. Untuk 
menggunakannya, kita bisa membuat direktori `~/.vim/pack/vendor/start/`, kemudian 
masukkan plugin yang ingin di install ke dalam direktori tersebut (contohnya via 
`git clone`).

Berikut beberapa _plugin_ yang kami rekomendasikan:

- [ctrlp.vim](https://github.com/ctrlpvim/ctrlp.vim): pencarian file 
- [ack.vim](https://github.com/mileszs/ack.vim): pencarian kode
- [nerdtree](https://github.com/scrooloose/nerdtree): penjelajah file
- [vim-easymotion](https://github.com/easymotion/vim-easymotion): magic motions

Tutorial ini menghindari memberikan daftar _plugin_ yang terlalu banyak. Anda
bisa melihat _dotfiles_ pengajar jika tertarik untuk mempelajari plugin-plugin
lain: ([Anish](https://github.com/anishathalye/dotfiles),
[Jon](https://github.com/jonhoo/configs),
[Jose](https://github.com/JJGO/dotfiles)) untuk melihat plugin lain yang biasa 
kami gunakan, anda bisa kunjungi halaman [Vim Awesome](https://vimawesome.com/) 
untuk plugin yang lebih menarik. Banyak sekali blog post yang membahas topik ini,
anda dapat menggunakan kata kunci "best Vim plugins" untuk mengunjunginya.

# Mode _Vim_ di program lain

Banyak tools yang sudah mendukung emulasi _Vim_. Namun, kualitas emulasinya bermacam-macam;
tergantung tools yang kita gunakan. Mungkin beberapa tidak mendukung fitur _Vim_
yang _advance_, namun, hampir semua tools tersebut sudah mendukung fitur dasar 
dengan baik.

## Shell

Jika anda pengguna _Bash_, gunakan `set -o vi`. Jika anda menggunakan Zsh, `bindkey -v`
untuk _Fish_, `fish_vi_key_bindings`. selanjutnya, apapun jenis shell yang anda gunakan,
anda bisa menggunakan `export EDITOR=vim`. Ini merupakan variabel environment yang 
digunakan untuk menentukan editor mana yang digunakan ketika sebuah program ingin membuka
sebuah editor. Contohnya, `git` akan menggunakan editor yang dipilih untuk menyisipkan
pesan dalam perintah _commit_.

## Readline

Banyak program memakai [GNU
Readline](https://tiswww.case.edu/php/chet/readline/rltop.html), library 
untuk antarmuka command-line mereka. Readline mendukung (dasar) emulasi _Vim_,
yang dapat diaktifkan dengan menambahkan baris berikut kedalam file `~/.inputrc`:

```
set editing-mode vi
```
Dengan pengaturan ini, sebagai contoh, Python REPL akan mendukung bindings _Vim_.


## Lain-lain

Bahkan, ekstensi keybinding _Vim_ pun tersedia untuk browser 
[web](http://vim.wikia.com/wiki/Vim_key_bindings_for_web_browsers) - beberapa 
yang populer antara lain adalah 
[Vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb?hl=en)
untuk Google Chrome dan [Tridactyl](https://github.com/tridactyl/tridactyl) 
untuk Firefox. Kita bahkan bisa mendapatkan keybinding _Vim_ untuk 
[Jupyter notebook](https://github.com/lambdalisue/jupyter-vim-binding). Berikut
adalah [daftar panjang](https://reversed.top/2016-08-13/big-list-of-vim-like-software) 
perangkat lunak yang memiliki keybinding yang mirip dengan _Vim_

# Vim lanjutan

Berikut adalah beberapa contoh kegunaan _Vim_ dengan fungsi yang lebih canggih.
Tidak semua kegunaan _Vim_ dijelaskan di halaman ini, namun, anda akan belajar
seiring dengan penggunaan _Vim_ untuk pekerjaan anda sehari-hari. Tips yang cukup
bagus: tiap kali anda mengunakan editor dan anda berpikir bahwa "Mungkin ada 
cara yang lebih baik untuk melakukan ini", mungkin anda benar dan cobalah untuk
mencarinya di internet.

## Cari dan ganti (search and replace)

`:s` perintah ganti (substitute) ([dokumentasi](http://vim.wikia.com/wiki/Search_and_replace)).

- `%s/foo/bar/g`
    - Ganti foo dengan bar secara global didalam file 
- `%s/\[.*\](\(.*\))/\1/g`
    - Ganti _named_ Markdown link dengan URL biasa

## Window lebih dari satu
- `:sp` / `:vsp` untuk membelah window
- Dapat menggunakan lebih dari satu view pada _buffer_ yang sama

## Macros

- `q{karakter}` untuk memulai merekam _macro_ dalam register `{karakter}`
- `q` untuk berhenti merekan 
- `@{karakter}` menjalankan ulang _macro_ 
- Eksekusi _macro_ berhenti ketika terjadi error 
- `{angka}@{karakter}` jalankan _macro_ {angka} kali
- _Macro_ dapat bersifat rekursif
    - hapus _macro_ dengan `q{character}q`
    - rekam _macro_, dengan `@{character}` untuk memanggilnya secara rekursif 
    (_no-op_ sampai perekaman selesai)
- Contoh: konversi xml ke json ([file](/2020/files/example-data.xml))
    - Object Array dengan key "name"/"email"
    - Menggunakan program Python? 
    - Menggunakan sed / regexes
        - `g/people/d`
        - `%s/<person>/{/g`
        - `%s/<name>\(.*\)<\/name>/"name": "\1",/g`
        - ...
    - Perintah _Vim_ / macros
        - `Gdd`, `ggdd` hapus baris pertama dan terakhir
        - _Macro_ untuk memformat elemen tunggal (register `e`)
            - Pergi ke baris yang memiliki `<name>`
            - `qe^r"f>s": "<ESC>f<C"<ESC>q`
        - _Macro_ untuk memformat _person_ 
            - Menuju baris yang memiliki `<person>`
            - `qpS{<ESC>j@eA,<ESC>j@ejS},<ESC>q`
        - _Macro_ untuk memformat _person_ dan menuju _person_ selanjutnya 
            - Menuju baris yang memiliki `<person>`
            - `qq@pjq`
        - Jalankan _macro_ sampai dengan baris terakhir dalam file 
            - `999@q`
        - Hapus `,` terakhir secara manual dan tambahkan delimiter `[` dan `]`

# Sumber

- `vimtutor` adalah tutorial yang telah terinstall dalam _Vim_ - 
jika _Vim_ sudah terinstall, kita dapat menjalankan `vimtutor` dari shell.
- [Vim Adventures](https://vim-adventures.com/) game untuk belajar _Vim_
- [Vim Tips Wiki](http://vim.wikia.com/wiki/Vim_Tips_Wiki)
- [Vim Advent Calendar](https://vimways.org/2019/) memiliki banyak tips _Vim_ 
- [Vim Golf](http://www.vimgolf.com/) mirip [code golf](https://en.wikipedia.org/wiki/Code_golf), 
Namun bahasa premrograman yang digunakan adalah UI dari _Vim_
- [Vi/Vim Stack Exchange](https://vi.stackexchange.com/)
- [Vim Screencasts](http://vimcasts.org/)
- [Practical Vim](https://pragprog.com/titles/dnvim2/) (buku)


# Latihan

1. Selesaikan `vimtutor`. Catatan: tampilannya akan terlihat bagus pada 
   [80x24](https://en.wikipedia.org/wiki/VT100) (80 kolom, 24 baris)
   terminal window.
1. Download [basic vimrc](/2020/files/vimrc) dan simpan dalam `~/.vimrc`. Baca 
   file dengan dokumentasi yang lengkap tersebut (Menggunakan _Vim_!)
   dan amati bagaimana _Vim_ berubah sedikit dengan konfigurasi baru tersebut.
1. Install dan ubah pengaturan plugin
   [ctrlp.vim](https://github.com/ctrlpvim/ctrlp.vim).
   1. Buat folder plugin menggunakan  `mkdir -p ~/.vim/pack/vendor/start`
   1. Download plugin: `cd ~/.vim/pack/vendor/start; git clone
      https://github.com/ctrlpvim/ctrlp.vim`
   1. Baca 
      [dokumentasi](https://github.com/ctrlpvim/ctrlp.vim/blob/master/readme.md)
      plugin yang ingin di install. Jalankan CtrlP untuk mencari file dengan menavigasi
      direktori project, buka _Vim_, kemudian jalankan `:CtrlP` pada command-line _Vim_.
    1. Ubah pengaturan CtrlP dengan menambahkan 
       [konfigurasi](https://github.com/ctrlpvim/ctrlp.vim/blob/master/readme.md#basic-options)
       pada file `~/.vimrc` untuk membuka CtrlP  dengan menekan Ctrl-P.
1. Untuk praktek menggunakan _Vim_, jalankan ulang [Demo](#demo) dari tutorial 
   ini menggunakan komputer anda sendiri.
1. Gunakan Vim untuk semua tugas editing teks anda untuk bulan depan. Jika anda
   mendapati suatu hal tidak efisien, atau ketika anda berfikir "mungkin ada cara
   yang lebih baik", anda bisa mencarinya menggunakan Google, kemungkinan besar
   anda akan menemukannya. Jika anda merasa buntu, anda bisa mengunjungi kami
   pada jam kerja, atau kirim email pada kami.
1. Ubah pengaturan tool lain anda menggunakan binding _Vim_ (lihat instruksi diatas)
1. Ubah lagi pengaturan `~/.vimrc` anda sesuai keinginan, dan tambahkan lagi plugin yang lain.
1. (Tingkat lanjut) Konversi XML ke JSON  ([contoh file](/2020/files/example-data.xml))
   menggunakan _macro_ pada _Vim_. Praktikan ini sendiri, namu jika anda buntu,
   anda dapat melihat bagian [macros](#macros) diatas.
