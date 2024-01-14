---
layout: lecture
title: "Editors (Vim)"
date: 2020-01-15
ready: true
video:
  aspect: 56.25
  id: a6Q8Na575qc
---

<!---
Writing English words and writing code are very different activities. When
programming, you spend more time switching files, reading, navigating, and
editing code compared to writing a long stream. It makes sense that there are
different types of programs for writing English words versus code (e.g.
Microsoft Word versus Visual Studio Code).
-->
Penulisan dokumen atau artikel dalam bahasa natural sangat berbeda dengan 
penulisan kode program. Saat menulis kode program, biasanya seorang programmer 
menghabiskan waktu lebih untuk berpindah antar file, membaca file yang berbeda, 
dan mengubah isi file-file tersebut dibanding fokus pada satu file dalam waktu 
yang lama seperti penulisan dokumen bahasa natural. Sehingga, cukup masuk akal 
jika program komputer yang digunakan dalam menulis bahasa natural berbeda dengan 
untuk menulis kode program (contohnya _Microsoft Word versus Visual Studio Code_).

<!--
As programmers, we spend most of our time editing code, so it's worth investing
time mastering an editor that fits your needs. Here's how you learn a new
editor:

- Start with a tutorial (i.e. this lecture, plus resources that we point out)
- Stick with using the editor for all your text editing needs (even if it slows
you down initially)
- Look things up as you go: if it seems like there should be a better way to do
something, there probably is
-->
Sebagai seorang _programmer_, kita menghabiskan banyak waktu dalam menulis dan 
mengedit kode program. Sehingga, penguasaan _editor_ yang cocok dengan kebutuhan 
kita sangatlah berguna untuk menambah produktifitas kerja kita. Untuk belajar 
_editor_ baru biasanya _programmer_ dapat melakukan langkah-langkah berikut:

- Mulai dengan mempelajari suatu tutorial (contoh. kuliah ini, dan sumber-sumber
materi yang terdapat pada dokumen ini)
- Fokus menggunakan _editor_ yang ingin dipelajari untuk keperluan sehari-hari
(Meskipun hal ini akan membuat pekerjaan menjadi agak lambat di awal penggunaan
editor)
- Mencari trik-trik baru dalam penggunaan _editor_ sesuai dengan kebutuhan anda
sebagai _programmer_

<!--
If you follow the above method, fully committing to using the new program for
all text editing purposes, the timeline for learning a sophisticated text
editor looks like this. In an hour or two, you'll learn basic editor functions
such as opening and editing files, save/quit, and navigating buffers. Once
you're 20 hours in, you should be as fast as you were with your old editor.
After that, the benefits start: you will have enough knowledge and muscle
memory that using the new editor saves you time. Modern text editors are fancy
and powerful tools, so the learning never stops: you'll get even faster as you
learn more. -->

Jika anda mengikuti metode diatas, dan selalu menggunakan _editor_ yang sedang 
dipelajari dalam tiap pekerjaan anda, perjalanan belajar anda akan seperti 
berikut: Dalam satu atau dua jam, anda akan mempelajari fungsi dasar _editor_ 
seperti, membuka dan mengedit _file_, penyimpanan/keluar aplikasi, dan navigasi 
_buffer_. Sesudah 20 jam, anda harusnya sudah sangat nyaman seperti menggunakan 
_editor_ yang biasa anda gunakan sebelumnya. Setelah itu, keunggulan menggunakan 
editor baru ini akan terasa: anda akan memiliki pengetahuan dan memori otot yang 
cukup dalam menggunakan _editor_ ini sehingga banyak waktu yang dapat dihemat.
_Editor_ teks modern merupakan _tools_ yang cukup _powerful_, dalam perjalanan 
menggunakan _editor_ ini, anda akan menemukan trik-trik baru yang membuat pekerjaan
anda semakin cepat dan efisien!

<!--
# Which editor to learn?

Programmers have [strong opinions](https://en.wikipedia.org/wiki/Editor_war)
about their text editors.

Which editors are popular today? See this [Stack Overflow
survey](https://insights.stackoverflow.com/survey/2019/#development-environments-and-tools)
(there may be some bias because Stack Overflow users may not be representative
of programmers as a whole). [Visual Studio
Code](https://code.visualstudio.com/) is the most popular editor.
[Vim](https://www.vim.org/) is the most popular command-line-based editor.
-->

# Editor apakah yang akan dipelajari?

_Programmer_ memiliki [Opini yang kuat](https://id.wikipedia.org/wiki/Perang_editor) 
tentang _editor_ teks terbaik versi mereka. 

Untuk melihat editor mana yang populer sekarang, anda bisa melihat 
[survey _Stack Oveflow_](https://insights.stackoverflow.com/survey/2019/#development-environments-and-tools)
(mungkin terdapat bias pada survey ini, karena pengguna _Stack Overflow_
tidak merepresentasikan komunitas programmer secara menyeluruh). [_Visual Studio
Code_](https://code.visualstudio.com/) adalah _editor_ terpopuler dalam survey 
tersebut. Dan [Vim](https://www.vim.org/) adalah _editor_ berbasis _command line_
yang paling populer.

<!--
## Vim

All the instructors of this class use Vim as their editor. Vim has a rich
history; it originated from the Vi editor (1976), and it's still being
developed today. Vim has some really neat ideas behind it, and for this reason,
lots of tools support a Vim emulation mode (for example, 1.4 million people
have installed [Vim emulation for VS code](https://github.com/VSCodeVim/Vim)).
Vim is probably worth learning even if you finally end up switching to some
other text editor.

It's not possible to teach all of Vim's functionality in 50 minutes, so we're
going to focus on explaining the philosophy of Vim, teaching you the basics,
showing you some of the more advanced functionality, and giving you the
resources to master the tool.
-->

## Vim
Semua pengajar dalam kelas ini menggunakan _Vim_ sebagai editor. Sejarah _Vim_  
cukup panjang. _Vim_ dikembangkan dari editor _Vi_ (1976), yang sampai sekarang
pun masih dikembangkan. _Vim_ memilki banyak fungsionalitas yang berguna, karena
alasan ini banyak _tools_ yang memiliki _support_ emulasi _Vim_ (contohnya, 1.4 
juta orang telah menginstall [Vim emulation untuk VS code](https://github.com/VSCodeVim/Vim)).
Karena alasan tersebut, Vim mungkin tetap sangat berguna untuk dipelajari, meskipun 
pada akhirnya anda memilih untuk menggunakan _editor_ lain.


<!--
# Philosophy of Vim

When programming, you spend most of your time reading/editing, not writing. For
this reason, Vim is a _modal_ editor: it has different modes for inserting text
vs manipulating text. Vim is programmable (with Vimscript and also other
languages like Python), and Vim's interface itself is a programming language:
keystrokes (with mnemonic names) are commands, and these commands are
composable. Vim avoids the use of the mouse, because it's too slow; Vim even
avoids using the arrow keys because it requires too much movement.

The end result is an editor that can match the speed at which you think.
-->

# Filosofi _Vim_

Ketika menulis kode program, anda akan menggunakan lebih banyak waktu anda untuk 
membaca dan mengedit, bukan menulis dalam waktu panjang pada satu file. Oleh sebab 
itu, Vim adalah editor _modal_: ia memiliki berbagai macam _mode_ untuk memyisipkan 
teks dan memanipulasi teks. _Vim_ adalah editor yang _programmable_ (menggunakan 
_Vimscript_ dan bahasa pemrograman lain seperti _Python_), dan antarmuka _Vim_ sendiri 
adalah bahasa pemrograman: tiap tombol keyboard (dengan penamaan yang mudah diingat)
merupakan perintah operasi, dan perintah operasi ini dapat digabungkan sesuai kebutuhan.
_Vim_ menghindari penggunaan mouse, karena dapat memperlambat proses kerja kita.
Selain mouse, _Vim_ juga menghinadari penggunaan tombol arah, karena penggunaannya dapat
memperlambat navigasi dalam file. 


<!--
# Modal editing

Vim's design is based on the idea that a lot of programmer time is spent
reading, navigating, and making small edits, as opposed to writing long streams
of text. For this reason, Vim has multiple operating modes.

- **Normal**: for moving around a file and making edits
- **Insert**: for inserting text
- **Replace**: for replacing text
- **Visual** (plain, line, or block): for selecting blocks of text
- **Command-line**: for running a command

Keystrokes have different meanings in different operating modes. For example,
the letter `x` in Insert mode will just insert a literal character 'x', but in
Normal mode, it will delete the character under the cursor, and in Visual mode,
it will delete the selection.

In its default configuration, Vim shows the current mode in the bottom left.
The initial/default mode is Normal mode. You'll generally spend most of your
time between Normal mode and Insert mode.

You change modes by pressing `<ESC>` (the escape key) to switch from any mode
back to Normal mode. From Normal mode, enter Insert mode with `i`, Replace mode
with `R`, Visual mode with `v`, Visual Line mode with `V`, Visual Block mode
with `<C-v>` (Ctrl-V, sometimes also written `^V`), and Command-line mode with
`:`.

You use the `<ESC>` key a lot when using Vim: consider remapping Caps Lock to
Escape ([macOS
instructions](https://vim.fandom.com/wiki/Map_caps_lock_to_escape_in_macOS)).
-->

# Modal editing

Design _Vim_ berdasarkan argumen bahwa banyak waktu _programmer_ dihabiskan untuk
membaca, menavigasi, dan melakukan perubahan dalam skala kecil pada file-file basis 
kode yang dikerjakan. Hal tersebut berbeda dengan penulisan teks yang banyak dan 
cenderun fokus pada satu file seperti pada penulisan dokumen atau artikel bahasa 
natural. Karena alasan tersebut, Vim memiliki beberapa mode operasi.

- **Normal**: untuk navigasi dalam file dan melakukan perubahan pada teks dalam file
- **Insert**: untuk menyisipkan teks
- **Replace**: untuk me-replace teks
- **Visual** (plain, line, atau block): untuk memilih blok teks
- **Command-line**: untuk menjalankan perintah

Tiap tombol memiliki kegunaan yang berbeda dalam mode operasi yang berbeda. 
Contohnya, tombol huruf 'x' dalam mode Insert berfungsi untuk menyisipkan huruf 
'x' seperti layaknya dalam teks editor umum. Namun, dalam mode Normal, tombol 
huruf 'x' berfungsi untuk menghapus huruf dalam kursor aktif. Lain pula dalam mode 
Visual, tombol tersebut akan menghapus teks yang terseleksi.

Dalam pengaturan defaultnya, _Vim_ menampilkan mode yang aktif di bagian kiri bawah.
Mode awal/default dalam _Vim_ adalah mode Normal. Saat menggunakan _Vim_, anda akan 
banyak menghabiskan waktu pada mode Normal dan mode Insert.

Kita dapat mengaktifkan atau kembali ke mode Normal dari mode lain dengan 
menekan '<ESC>' (tombol escape). Dari mode Normal, kita bisa menekan tombol 'i' 
untuk mengaktifkan mode Insert, tombol 'R' untuk mode Replace, tombol 'v' untuk mode
Visual, 'V' untuk mode Visual Line, '<C-v>' (Ctrl-V, kadang ditulis juga dengan '^V')
untuk Visual mode Visual Block, dan tombol ':' untuk mode Command-line. 

Kita akan menggunakan tombol '<ESC>' cukup sering ketika menggunakan _Vim_: salah 
satu tips agar jangkauannya menjadi lebih dekat, adalah dengan melakukan _remapping_
Caps Lock ke tombol Escape ([instruksi untuk pengguna 
macOS](https://vim.fandom.com/wiki/Map_caps_lock_to_escape_in_macOS)).

<!--
# Basics

## Inserting text

From Normal mode, press `i` to enter Insert mode. Now, Vim behaves like any
other text editor, until you press `<ESC>` to return to Normal mode. This,
along with the basics explained above, are all you need to start editing files
using Vim (though not particularly efficiently, if you're spending all your
time editing from Insert mode).

-->

# Dasar-dasar Vim

## Menyisipkan teks

Dalam mode Normal, tekan 'i' untuk masuk kedalam mode Insert. Dalam mode ini,
Vim bekerja seperti teks editor pada umumnya. Untuk kembali ke mode Normal, 
kita dapat menekan tombol '<ESC>'. Kedua hal ini cukup untuk memulai menggunakan
_Vim_ (Namun hal ini akan sangat tidak efisien, terutama karena kita menghabiskan
waktu kita untuk melakukan editing dalam mode Insert).

<!--
## Buffers, tabs, and windows

Vim maintains a set of open files, called "buffers". A Vim session has a number
of tabs, each of which has a number of windows (split panes). Each window shows
a single buffer. Unlike other programs you are familiar with, like web
browsers, there is not a 1-to-1 correspondence between buffers and windows;
windows are merely views. A given buffer may be open in _multiple_ windows,
even within the same tab. This can be quite handy, for example, to view two
different parts of a file at the same time.

By default, Vim opens with a single tab, which contains a single window.
-->

## Buffer, tab, dan window

"Buffer" adalah file-file yang sedang di tangani/dibuka oleh _Vim_. Suatu sesi 
_Vim_ biasanya memiliki beberapa tab, dimana tiap tabnya memilki beberapa window. 
Setiap window menampilkan sebuah buffer. Berbeda dengan program komputer yang 
biasa kita pakai, seperti browser web, buffer dan window tidak memilki hubungan 
satu satu (1-to-1); windows hanya berfungsi sebagai view (menampilkan buffer).
Satu buffer dapat dibuka dengan lebih dari satu window, meski dalam satu tab 
yang sama. Hal ini sangat berguna, contohnya ketika kita ingin melihat bagian
berbeda dalam satu file secara bersamaan. 

Dalam kondisi default, _Vim_ akan terbuka dengan satu tab, yang berisi satu
window.

<!--
## Command-line

Command mode can be entered by typing `:` in Normal mode. Your cursor will jump
to the command line at the bottom of the screen upon pressing `:`. This mode
has many functionalities, including opening, saving, and closing files, and
[quitting Vim](https://twitter.com/iamdevloper/status/435555976687923200).

- `:q` quit (close window)
- `:w` save ("write")
- `:wq` save and quit
- `:e {name of file}` open file for editing
- `:ls` show open buffers
- `:help {topic}` open help
    - `:help :w` opens help for the `:w` command
    - `:help w` opens help for the `w` movement
-->

## Mode command-line

Kita dapat masuk kedalam mode command-line dengan cara menekan tombol ':' pada 
mode Normal. Kursor akan berpindah ke baris perintah saat tombol ':' ditekan. Mode
ini memiliki banyak kegunaan, seperti membuka, menyimpan dan menutup file. Dan
tak lupa untuk [menutup _Vim_](https://twitter.com/iamdevloper/status/435555976687923200).

- ':q' keluar ('quit', menutup window)
- ':w' simpan ('write')
- ':wq' simpan dan keluar
- ':e {nama file}' buka file untuk editing
- ':ls' menampilkan buffer-buffer yang terbuka
- ':help {topik}' membuka panduan _Vim_
    - ':help :w' membuka panduan untuk perintah ':w'
    - ':help w' membuka panduan untuk tombol 'w'

<!--
# Vim's interface is a programming language

The most important idea in Vim is that Vim's interface itself is a programming
language. Keystrokes (with mnemonic names) are commands, and these commands
_compose_. This enables efficient movement and edits, especially once the
commands become muscle memory.
-->

# Antarmuka _Vim_ sebagai bahasa pemrograman

Salah satu hal terpenting dalam _Vim_ adalah antarmuka _Vim_ sendiri merupakan
sebuah bahasa pemrograman. Tombol keyboard (dengan penamaan yang mudah diingat) 
adalah perintah, dan perintah-perintah ini dapat digabungkan satu sama lain. 
Hal tersebut dapat menambah efisiensi dalam pergerakan dan penyuntingan teks 
atau kode program. Terutama saat pengguna hapal diluar kepala akan perintah-perintah
yang ada. 

<!--
## Movement

You should spend most of your time in Normal mode, using movement commands to
navigate the buffer. Movements in Vim are also called "nouns", because they
refer to chunks of text.

- Basic movement: `hjkl` (left, down, up, right)
- Words: `w` (next word), `b` (beginning of word), `e` (end of word)
- Lines: `0` (beginning of line), `^` (first non-blank character), `$` (end of line)
- Screen: `H` (top of screen), `M` (middle of screen), `L` (bottom of screen)
- Scroll: `Ctrl-u` (up), `Ctrl-d` (down)
- File: `gg` (beginning of file), `G` (end of file)
- Line numbers: `:{number}<CR>` or `{number}G` (line {number})
- Misc: `%` (corresponding item)
- Find: `f{character}`, `t{character}`, `F{character}`, `T{character}`
    - find/to forward/backward {character} on the current line
    - `,` / `;` for navigating matches
- Search: `/{regex}`, `n` / `N` for navigating matches
-->
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


<!--
## Selection

Visual modes:

- Visual: `v`
- Visual Line: `V`
- Visual Block: `Ctrl-v`

Can use movement keys to make selection.
-->

## Seleksi

Mode visual:

- Visual: `v`
- Visual line: `V`
- Visual Block: `Ctrl-v`

Dengan menggunakan mode ini kita dapat menggunakan tombol gerak
untuk menyeleksi teks secara visual. 


<!--
## Edits

Everything that you used to do with the mouse, you now do with the keyboard
using editing commands that compose with movement commands. Here's where Vim's
interface starts to look like a programming language. Vim's editing commands
are also called "verbs", because verbs act on nouns.

- `i` enter Insert mode
    - but for manipulating/deleting text, want to use something more than
    backspace
- `o` / `O` insert line below / above
- `d{motion}` delete {motion}
    - e.g. `dw` is delete word, `d$` is delete to end of line, `d0` is delete
    to beginning of line
- `c{motion}` change {motion}
    - e.g. `cw` is change word
    - like `d{motion}` followed by `i`
- `x` delete character (equal do `dl`)
- `s` substitute character (equal to `xi`)
- Visual mode + manipulation
    - select text, `d` to delete it or `c` to change it
- `u` to undo, `<C-r>` to redo
- `y` to copy / "yank" (some other commands like `d` also copy)
- `p` to paste
- Lots more to learn: e.g. `~` flips the case of a character
-->

## Edit 

Pekerjaan yang biasanya bisa kita kerjakan menggunakan mouse, dapat kita kerjakan
menggunakan keyboard dengan perintah editing digabungkan dengan perintah pergerakan.
Dengan melakukan hal tersebut antarmuka _Vim_ mulai mirip dengan bahasa pemrograman.
Perintah editing dalam _Vim_ dikenal juga dengan "verbs", karena (dalam bahasa inggris)
verbs bertindak pada nouns.

- `i` masuk keadalam mode Insert
    - namun untuk memanipulasi/menghapus teks, kita ingin menggunakan cara lain 
    selain tombol backspace
- `o` / `O` sisipkan baris baru di bawah/atas kursor aktif
- `d{pergerakan}` menghapus (delete) {pergerakan}
    - Contoh: `dw` digunakan untuk menghapus kata (word), `d$` hapus sampai akhir baris,
    `d0` hapus sampai awal baris
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
- Banyak perintah lain juga untuk dipelajari: contoh `-` untuk mebalik _case_ sebuah 
huruf.


<!--
## Counts

You can combine nouns and verbs with a count, which will perform a given action
a number of times.

- `3w` move 3 words forward
- `5j` move 5 lines down
- `7dw` delete 7 words
-->

## Hitungan (Counts)

Kita dapat mengkombinasikan nouns dan verbs dengan counts. Dengan enggunakan counts,
perintah kita akan dilakukan sebanyak sekian kali.

- `3w` berpindah 3 huruf kedepan
- `5j` berpindah 3 baris kebawah
- `7dw` hapus 7 huruf


<!--
## Modifiers

You can use modifiers to change the meaning of a noun. Some modifiers are `i`,
which means "inner" or "inside", and `a`, which means "around".

- `ci(` change the contents inside the current pair of parentheses
- `ci[` change the contents inside the current pair of square brackets
- `da'` delete a single-quoted string, including the surrounding single quotes
-->

## Modifiers

Kita dapat menggunakan modifiers untuk mengubah "arti" dari sebuah noun. 
Salah satu modifiers yang sering digunakan adalah `i`, yang artinya "inner"
atau "inside" (di dalam). Kemudian`a`, yang artinya "around" (sekitar).

- `ci(` ubah konten di dalam tanda kurung ()
- `ci[` ubah konten didalam tanda kurung []
- `da'` hapus string tanda petik satu `'`, termasuk string di sekitarnya

<!--
# Demo

Here is a broken [fizz buzz](https://en.wikipedia.org/wiki/Fizz_buzz)
implementation:

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

We will fix the following issues:

- Main is never called
- Starts at 0 instead of 1
- Prints "fizz" and "buzz" on separate lines for multiples of 15
- Prints "fizz" for multiples of 5
- Uses a hard-coded argument of 10 instead of taking a command-line argument

{% comment %}
- main is never called
  - `G` end of file
  - `o` open new line below
  - type in "if __name__ ..." thing
- starts at 0 instead of 1
  - search for `/range`
  - `ww` to move forward 2 words
  - `i` to insert text, "1, "
  - `ea` to insert after limit, "+1"
- newline for "fizzbuzz"
  - `jj$i` to insert text at end of line
  - add ", end=''"
  - `jj.` to repeat for second print
  - `jjo` to open line below if
  - add "else: print()"
- fizz fizz
  - `ci'` to change fizz
- command-line argument
  - `ggO` to open above
  - "import sys"
  - `/10`
  - `ci(` to "int(sys.argv[1])"
{% endcomment %}

See the lecture video for the demonstration. Compare how the above changes are
made using Vim to how you might make the same edits using another program.
Notice how very few keystrokes are required in Vim, allowing you to edit at the
speed you think.
-->

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

<!--
# Customizing Vim

Vim is customized through a plain-text configuration file in `~/.vimrc`
(containing Vimscript commands). There are probably lots of basic settings that
you want to turn on.

We are providing a well-documented basic config that you can use as a starting
point. We recommend using this because it fixes some of Vim's quirky default
behavior. **Download our config [here](/2020/files/vimrc) and save it to
`~/.vimrc`.**

Vim is heavily customizable, and it's worth spending time exploring
customization options. You can look at people's dotfiles on GitHub for
inspiration, for example, your instructors' Vim configs
([Anish](https://github.com/anishathalye/dotfiles/blob/master/vimrc),
[Jon](https://github.com/jonhoo/configs/blob/master/editor/.config/nvim/init.vim) (uses [neovim](https://neovim.io/)),
[Jose](https://github.com/JJGO/dotfiles/blob/master/vim/.vimrc)). There are
lots of good blog posts on this topic too. Try not to copy-and-paste people's
full configuration, but read it, understand it, and take what you need.
-->

# Pengaturan _Vim_

Untuk membuat _Vim_ menjadi seperti yang kita inginkan, kita dapat mengubah
pengaturan _Vim_ melalui file '~/.vimrc' (yang berisi perintah perintah _Vimscript_).
Mungkin ada beberapa penaturan yang ingin kita aktifkan untuk mempermudah 
pekerjaan kita.

Tutorial ini menyediakan konfigurasi dasar yang terdokumentasi dengan baik
untuk kita gunakan sebagai file konfigurasi awal kita. Kami merekomendasikan
untuk memakai konfigurasi ini, agar beberapa hal yang kurang praktis dari 
pengaturan default _Vim_ bisa dihindari.  **Silahkan unduh konfigurasi
tersebut [disini](/2020/files/vimrc) dan simpan ke dalam `~/.vimrc`.**

Pengaturan _Vim_ sangatlah kaya dan fleksibel, dan mempelajari berbagai macam
opsi pengaturan dalam _Vim_ sangatlah direkomendasikan. Anda dapat melihat 
_ditfiles_ pengguna _Vim_ lain di GitHub sebagai referensi untuk konfigurasi anda.
Sebagai contoh konfigurasi _Vim_ pengajar turorial ini dapat dilihat di:  
([Anish](https://github.com/anishathalye/dotfiles/blob/master/vimrc),
[Jon](https://github.com/jonhoo/configs/blob/master/editor/.config/nvim/init.vim) (uses [neovim](https://neovim.io/)),
[Jose](https://github.com/JJGO/dotfiles/blob/master/vim/.vimrc)). Selain
referensi diatas banyak juga postingan blog bagus yang membahas topik ini.
Cobalah untuk tidak hanya melakukan _copy-paste_ konfigurasi pengguna _Vim_
lain, namun baca, pahami, dan ambil bagian bagian yang anda butuhkan.

# Extending Vim

There are tons of plugins for extending Vim. Contrary to outdated advice that
you might find on the internet, you do _not_ need to use a plugin manager for
Vim (since Vim 8.0). Instead, you can use the built-in package management
system. Simply create the directory `~/.vim/pack/vendor/start/`, and put
plugins in there (e.g. via `git clone`).

Here are some of our favorite plugins:

- [ctrlp.vim](https://github.com/ctrlpvim/ctrlp.vim): fuzzy file finder
- [ack.vim](https://github.com/mileszs/ack.vim): code search
- [nerdtree](https://github.com/scrooloose/nerdtree): file explorer
- [vim-easymotion](https://github.com/easymotion/vim-easymotion): magic motions

We're trying to avoid giving an overwhelmingly long list of plugins here. You
can check out the instructors' dotfiles
([Anish](https://github.com/anishathalye/dotfiles),
[Jon](https://github.com/jonhoo/configs),
[Jose](https://github.com/JJGO/dotfiles)) to see what other plugins we use.
Check out [Vim Awesome](https://vimawesome.com/) for more awesome Vim plugins.
There are also tons of blog posts on this topic: just search for "best Vim
plugins".

# Vim-mode in other programs

Many tools support Vim emulation. The quality varies from good to great;
depending on the tool, it may not support the fancier Vim features, but most
cover the basics pretty well.

## Shell

If you're a Bash user, use `set -o vi`. If you use Zsh, `bindkey -v`. For Fish,
`fish_vi_key_bindings`. Additionally, no matter what shell you use, you can
`export EDITOR=vim`. This is the environment variable used to decide which
editor is launched when a program wants to start an editor. For example, `git`
will use this editor for commit messages.

## Readline

Many programs use the [GNU
Readline](https://tiswww.case.edu/php/chet/readline/rltop.html) library for
their command-line interface. Readline supports (basic) Vim emulation too,
which can be enabled by adding the following line to the `~/.inputrc` file:

```
set editing-mode vi
```

With this setting, for example, the Python REPL will support Vim bindings.

## Others

There are even vim keybinding extensions for web
[browsers](http://vim.wikia.com/wiki/Vim_key_bindings_for_web_browsers) - some
popular ones are
[Vimium](https://chrome.google.com/webstore/detail/vimium/dbepggeogbaibhgnhhndojpepiihcmeb?hl=en)
for Google Chrome and [Tridactyl](https://github.com/tridactyl/tridactyl) for
Firefox. You can even get Vim bindings in [Jupyter
notebooks](https://github.com/lambdalisue/jupyter-vim-binding).
Here is a [long list](https://reversed.top/2016-08-13/big-list-of-vim-like-software) of software with vim-like keybindings.

# Advanced Vim

Here are a few examples to show you the power of the editor. We can't teach you
all of these kinds of things, but you'll learn them as you go. A good
heuristic: whenever you're using your editor and you think "there must be a
better way of doing this", there probably is: look it up online.

## Search and replace

`:s` (substitute) command ([documentation](http://vim.wikia.com/wiki/Search_and_replace)).

- `%s/foo/bar/g`
    - replace foo with bar globally in file
- `%s/\[.*\](\(.*\))/\1/g`
    - replace named Markdown links with plain URLs

## Multiple windows

- `:sp` / `:vsp` to split windows
- Can have multiple views of the same buffer.

## Macros

- `q{character}` to start recording a macro in register `{character}`
- `q` to stop recording
- `@{character}` replays the macro
- Macro execution stops on error
- `{number}@{character}` executes a macro {number} times
- Macros can be recursive
    - first clear the macro with `q{character}q`
    - record the macro, with `@{character}` to invoke the macro recursively
    (will be a no-op until recording is complete)
- Example: convert xml to json ([file](/2020/files/example-data.xml))
    - Array of objects with keys "name" / "email"
    - Use a Python program?
    - Use sed / regexes
        - `g/people/d`
        - `%s/<person>/{/g`
        - `%s/<name>\(.*\)<\/name>/"name": "\1",/g`
        - ...
    - Vim commands / macros
        - `Gdd`, `ggdd` delete first and last lines
        - Macro to format a single element (register `e`)
            - Go to line with `<name>`
            - `qe^r"f>s": "<ESC>f<C"<ESC>q`
        - Macro to format a person
            - Go to line with `<person>`
            - `qpS{<ESC>j@eA,<ESC>j@ejS},<ESC>q`
        - Macro to format a person and go to the next person
            - Go to line with `<person>`
            - `qq@pjq`
        - Execute macro until end of file
            - `999@q`
        - Manually remove last `,` and add `[` and `]` delimiters

# Resources

- `vimtutor` is a tutorial that comes installed with Vim - if Vim is installed, you should be able to run `vimtutor` from your shell
- [Vim Adventures](https://vim-adventures.com/) is a game to learn Vim
- [Vim Tips Wiki](http://vim.wikia.com/wiki/Vim_Tips_Wiki)
- [Vim Advent Calendar](https://vimways.org/2019/) has various Vim tips
- [Vim Golf](http://www.vimgolf.com/) is [code golf](https://en.wikipedia.org/wiki/Code_golf), but where the programming language is Vim's UI
- [Vi/Vim Stack Exchange](https://vi.stackexchange.com/)
- [Vim Screencasts](http://vimcasts.org/)
- [Practical Vim](https://pragprog.com/titles/dnvim2/) (book)

# Exercises

1. Complete `vimtutor`. Note: it looks best in a
   [80x24](https://en.wikipedia.org/wiki/VT100) (80 columns by 24 lines)
   terminal window.
1. Download our [basic vimrc](/2020/files/vimrc) and save it to `~/.vimrc`. Read
   through the well-commented file (using Vim!), and observe how Vim looks and
   behaves slightly differently with the new config.
1. Install and configure a plugin:
   [ctrlp.vim](https://github.com/ctrlpvim/ctrlp.vim).
   1. Create the plugins directory with `mkdir -p ~/.vim/pack/vendor/start`
   1. Download the plugin: `cd ~/.vim/pack/vendor/start; git clone
      https://github.com/ctrlpvim/ctrlp.vim`
   1. Read the
      [documentation](https://github.com/ctrlpvim/ctrlp.vim/blob/master/readme.md)
      for the plugin. Try using CtrlP to locate a file by navigating to a
      project directory, opening Vim, and using the Vim command-line to start
      `:CtrlP`.
    1. Customize CtrlP by adding
       [configuration](https://github.com/ctrlpvim/ctrlp.vim/blob/master/readme.md#basic-options)
       to your `~/.vimrc` to open CtrlP by pressing Ctrl-P.
1. To practice using Vim, re-do the [Demo](#demo) from lecture on your own
   machine.
1. Use Vim for _all_ your text editing for the next month. Whenever something
   seems inefficient, or when you think "there must be a better way", try
   Googling it, there probably is. If you get stuck, come to office hours or
   send us an email.
1. Configure your other tools to use Vim bindings (see instructions above).
1. Further customize your `~/.vimrc` and install more plugins.
1. (Advanced) Convert XML to JSON ([example file](/2020/files/example-data.xml))
   using Vim macros. Try to do this on your own, but you can look at the
   [macros](#macros) section above if you get stuck.
