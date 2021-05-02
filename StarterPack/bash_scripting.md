# Bash Scripting

Bash script adalah file yang berisi kumpulan command. Dengan bash script, kita bisa memudahkan tugas umum yang cukup rumit yang memerlukan banyak command.

# Table of Contents

- [Dasar Bash Scripting](#dasar-bash-scripting)
- [Variabel](#variabel)
    - [Variabel Spesial](#variabel-spesial)
- [Input User](#input-user)
- [Operasi Aritmatika](#operasi-aritmatika)
    - [let](#let)
    - [expr]($expr)
    - [Kurung Ganda](#kurung-ganda)
    - [Panjang Variabel](#panjang-variabel)
- [Percabangan](#percabangan)
    - [If](#if)
    - [Nested If](#nested-if)
    - [Else](#else)
    - [Elif](#elif)
    - [Case](#case)
    - [Operasi Boolean](#operasi-boolean)
- [Perulangan](#perulangan)
    - [While](#while)
    - [Until](#until)
    - [For](#for)
        - [Foreach](#foreach)
        - [Range-Based](#range-based)
    - [Break dan Continue](#break-dan-continue)
- [Fungsi](#fungsi)

## Dasar Bash Scripting

Poin penting untuk diingat adalah: **Semua yang bisa dikerjakan di Command Line bisa dimasukkan ke dalam Script, dan semua yang bisa dikerjakan di Script bisa dikerjakan di Command Line**.

Berikut adalah command untuk menjalankan/mengeksekusi Bash Script.

`./<nama_file>`

Jika muncul error *Permission Denied*, berarti script tersebut belum mendapatkan izin untuk dieksekusi. Izin eksekusi dapat diberikan dengan command `chmod 755 <nama_file>`.

## Variabel

Variabel adalah tempat sementara untuk menaruh data. Variabel dibuat dengan command:

`<nama_variabel>=<nilai_variabel>`

Variabel dapat dipanggil dengan command `$<nama_variabel>`.

### Variabel Spesial

Ada beberapa variabel yang sudah diatur oleh sistem.

- `$0` -> Nama dari file script.
- `$1 - $9` -> 9 argumen pertama yang diberikan kepada script saat dieksekusi.
- `$#` -> Jumlah argumen yang diberikan kepada script.
- `$@` -> Semua argumen yang diberikan kepada script.
- `$?` -> *Exit status* dari proses yang terakhir dijalankan.
- `$$` -> *Process ID* dari proses script.
- `$USER` -> Username dari user yang menjalankan script.
- `$HOSTNAME` -> Hostname dari komputer yang menjalankan script.
- `$SECONDS` -> Jumlah detik sejak script dijalankan.
- `$RANDOM` -> Angka acak.
- `$LINENO` -> Nomor baris kode.

## Input User

- `read [argumen] <nama_variabel>` -> menerima input dari user dan menyimpannya ke variabel `<nama_variabel>`.
    - `-p <teks>` -> Menampilkan teks sebelum menerima input.
    - `-s <teks>` -> Membuat *silent input* (input tidak ditampilkan).

## Operasi Aritmatika

### let

`let <operasi_aritmatika>`

Fungsi untuk menjalankan hitung-hitungan sederhana.

Contoh:

```
let a=2+3
echo $a    # 5
```

- `+` -> Penjumlahan
- `-` -> Pengurangan
- `\*` -> Perkalian
- `/` -> Pembagian
- `++` -> Increment
- `--` -> Decrement
- `%` -> Modulo/Sisa bagi

### expr

`expr <operasi_aritmatika>`

Mirip seperti `let`, tetapi hasil perhitungan langsung diprint.

Contoh:

```
expr 2\*3    # 6
```

### Kurung Ganda

`$((<operasi_aritmatika>))`

Mirip seperti `let`, tetapi operasi aritmatika diletakkan di dalam kurung ganda.

Contoh:
```
a=$((5%2))
echo $a    # 1
```

### Panjang Variabel

`$(#<nama_variabel>)`

Mendapatkan jumlah karakter dalam sebuah variabel.

Contoh:
```
a=420
echo $a    # 3
```

## Percabangan

### If

```
if [ <kondisi> ]
then
    <script>
fi
```

Script di antara `then` dan `fi` hanya akan dieksekusi apabila kondisi bernilai *true*.

Contoh:

```
a=3
if [ $a -gt 1 ]
then
    echo $a lebih besar dari 1
fi
```

### Nested If

Nested If adalah pembuatan if statement di dalam sebuah if statement.

Contoh:

```
a=3
if [ $a -gt 1 ]
then
    echo $a lebih besar dari 1
    if (( $a % 2 == 0 ))
    then
        echo $a juga merupakan bilangan genap
    fi
fi
```

### Else

```
if [ <kondisi> ]
then
    <script>
else
    <script>
fi
```

Else adalah ekstensi dari if, yang dijalankan ketika kondisi bernilai *false*.

Contoh:

```
a=3
if (( $a % 2 == 0 ))
then
    echo $a merupakan bilangan genap
else
    echo $a merupakan bilangan ganjil
fi
```

### Elif

```
if [ <kondisi> ]
then
    <script>
elif [ <kondisi ]
then
    <script>
fi
```

Elif adalah ekstensi dari if, yang memiliki kondisi yang akan dicek ketika kondisi sebelum elif bernilai *false*.

Contoh:

```
a=180
if [ $a -gt 1000 ]
then
    echo $a sangat besar
elif [ $a -gt 100 ]
then
    echo $a cukup besar
else
    echo $a tidak cukup besar
fi
```

### Case

```
case <variabel> in
    <pattern_1>)
        <command>
        ;;
    <pattern_2>)
        <command>
        ;;
    ...
esac
```

Dalam case, variabel akan dibandingkan dengan pattern, dan jika memenuhi, maka command di bawah case dari pattern tersebut akan dijalankan.

```
a=3
case $a in
    1)
        echo Senin
        ;;
    2)
        echo Selasa
        ;;
    3)
        echo Rabu
        ;;
    *)
        echo Gatau
        ;;
esac
```

### Operasi Boolean

- `&&` -> and, dimana kedua kondisi harus bernilai *true*
- `||` -> or, dimana hanya salah satu kondisi yang harus bernilai *true*

Contoh:

```
a=18
if (( a % 2 == 0 )) && (( a % 3 == 0 ))
then
    echo $a genap dan kelipatan 3
else
    echo $a biasa saja
fi
```

## Perulangan

### While

```
while [ <kondisi> ]
do
    <command>
done
```

Dalam while loop, command akan dieksekusi secara berulang selama kondisi bernilai *true*.

Contoh:

```
a=10
while [ $a -gt 0 ]
do
    echo $a
    let a--
done
```

### Until

```
until [ <kondisi> ]
do
    <command>
done
```

Until mirip seperti While, tetapi command akan dieksekusi sampai kondisi bernilai *true*.

### For

#### Foreach

```
for <variabel> in $<list>
do
    <command>
done
```

For loop akan menjalankan command dengan variabel yang nilainya berupa masing-masing elemen pada sebuah list.

Contoh:
```
list=(Aa Bb Cc Dd Ee Ff)
for i in $list
do
    echo $i
done
```

#### Range-Based

```
for <variabel> in {<int>..<int>}
do
    <command>
done
```

For loop juga bisa memproses barisan bilangan (range).

### Break dan Continue

- `break` -> Langsung keluar dari perulangan.
- `continue` -> Langsung melewati 1 iterasi perulangan.

## Fungsi

```
<nama_fungsi> () {
    <command>
}
```
```
function <nama_fungsi> {
    <command>
}
```

Fungsi dalam Bash adalah kumpulan kode yang bisa dipanggil kapanpun di dalam script.
