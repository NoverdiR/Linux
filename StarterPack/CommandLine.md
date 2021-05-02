<!-- Required extensions: mdx_math(enable_dollar_delimiter=1) -->

# Linux Command Line

Linux memiliki antarmuka GUI yang bekerja seperti GUI pada Windows maupun OS X. Namun, Linux memiliki antarmuka CLI yang sangat powerful dan bermanfaat untuk melakukan berbagai macam hal. CLI (Command Line Interface) adalah antarmuka sistem yang berbasis teks dan command. Dalam Linux, kita bisa memasukkan command melalui Terminal. 

# Table of Contents

- [Dasar Command Line](#dasar-command-line)
- [Manual](#manual)
    - [Jenis Tanda Kurung pada Manual](#jenis-tanda-kurung-pada-manual)
- [Navigasi Direktori](#navigasi-direktori)
- [Manipulasi File](#manipulasi-file)
- [Modifikasi File](#modifikasi-file)
- [Wildcard](#wildcard)
- [Grep](#grep)
- [Manajemen Proses](#manajemen-proses)

## Dasar Command Line

Seperti yang sudah dijelaskan sebelumnya, kita bisa memasukkan command melalui Terminal. Terminal pada Linux adalah program tempat menjalankan shell. Shell adalah program yang memproses command dan mengeluarkan output. Shell di Linux berupa Bash Script. Berikut adalah beberapa cara membuka Terminal:

1. Klik kanan pada desktop -> Open in Terminal
2. Ctrl + Alt + T
3. Melalui Applications List

Command yang kita masukkan bisa memiliki beberapa argumen. Argumen bisa diibaratkan sebagai 'variabel' yang bisa kita berikan kepada command agar command bekerja dengan cara yang agak berbeda. Argumen sendiri bersifat opsional.

Command yang kita masukkan pada Terminal pada umumnya memiliki format sebagai berikut: `<command> [argumen1] [argumen2] [argumen3] ...`

## Manual

Manual adalah bentuk dokumentasi dari setiap command yang terdapat dalam sistem, yang berisi fungsi, cara menjalankannya, dan apa saja argumen yang tersedia dari command tersebut.

1. `man <command>` -> Menampilkan manual dari suatu command.
2. `man -k <keyword>` -> Mencari keyword dari keseluruhan manual dan menampilkan informasi terkait.

Untuk keluar dari manual, tekan `q`.

### Jenis Tanda Kurung pada Manual

Ini juga berlaku untuk tanda kurung pada command dalam markdown ini.

- `[]` -> Opsional
- `<>` -> Wajib
- `...` -> Input bisa lebih dari satu
- `[x|y]` -> Pilih salah satu antara x dan y

## Navigasi Direktori

Berikut adalah daftar command untuk untuk bernavigasi melalui direktori-direktori menggunakan Command Line.

1. `pwd` -> Menampilkan direktori tempat kita berada sekarang.
2. `ls [argumen]` -> Menampilkan daftar file atau direktori.
    - `-a` -> Argumen untuk memasukkan file dan direktori _hidden_.
    - `-l` -> Argumen untuk menampilkan informasi mendetail dari setiap file dan direktori.
3. `cd <direktori>` -> Digunakan untuk berpindah direktori.
    - Direktori di Linux terbagi menjadi 2, yaitu _relative path_ dan _absolute path_. _Relative path_ adalah direktori yang relatif dengan posisi direktori kita sekarang, sedangkan _absolute path_ adalah direktori yang relatif dengan lokasi _root_.

## Manipulasi File

1. `file <nama_file>` -> Menentukan jenis dari suatu file.
2. `cat <nama_file>` -> Melihat isi dari file.
3. `less <nama_file>` -> Melihat isi dari file per halaman (sesuai ukuran Terminal).
2. `mkdir [argumen] <nama_direktori>` -> Membuat direktori baru di direktori sekarang.
    - `-v` -> Argumen agar command memberikan respon balik setelah membuat direktori.
3. `rmdir [argumen] <nama_direktori>` -> Menghapus direktori yang ditentukan.
    - `-v` -> Argumen agar command memberikan respon balik setelah membuat direktori.
4. `touch <nama_file>` -> Membuat file kosong.
5. `cp [argumen] <asal> <tujuan>` -> Menyalin sebuah file atau direktori.
6. `mv [argumen] <asal> <tujuan>` -> Memindahkan sebuah file atau direktori.
7. `rm [argumen] <nama_file>` -> Menghapus sebuah file.
    - `-r` -> Argumen untuk menghapus direktori yang berisi file.

## Modifikasi File

Untuk memodifikasi file melalui Terminal, kita bisa menggunakan ***Vi Text Editor***, melalui command `vi <nama_file>`. Vi memiliki 2 mode, yaitu Insert Mode dan Edit Mode. Kita bisa berpindah antar mode menggunakan `esc`. Dalam Insert Mode, kita bisa memodifikasi teks di dalam sebuah file tersebut. Dalam Edit Mode, kita bisa memasukkan command-command dari Vi itu sendiri.

1. `ZZ` atau `:wq` -> Save dan exit
2. `:q!` -> Exit tanpa save
3. `:w` -> Save tanpa exit

## Wildcard

Wildcard adalah 'building block' dalam membuat pattern yang bisa digunakan sebagai tambahan untuk command lainnya. Dasar dari wildcard adalah:

- `*` -> Merepresentasikan nol atau lebih karakter
- `?` -> Merepresentasikan satu karakter
- `[]` -> Merepresentasikan karakter dalam rentang tertentu

Contohnya, jika kita ingin agar `ls` hanya menampilkan file dan direktori yang berawalan huruf a, maka kita bisa menggunakan command `ls a*`.

## Grep

Grep adalah program yang berfungsi untuk menganalisis sebuah file dan menampilkan semua baris pada file tersebut yang mengandung sebuah pattern.

`grep [argumen] <pattern> <path_file>`

## Manajemen Proses

1. `top` -> Untuk melihat proses yang sedang berjalan secara *realtime*.
2. `ps [argumen]` -> Untuk melihat proses yang berjalan di Terminal tepat saat command dieksekusi.
    - `-aux` -> Argumen untuk melihat seluruh proses yang sedang berjalan di sistem.
3. `kill <process_id>` -> Menterminasi proses yang sedang berjalan. PID (process id) dapat dilihat melalui command `top` maupun `ps`.
