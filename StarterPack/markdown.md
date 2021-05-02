# Markdown

Markdown adalah *markup language* ringan yang dapat digunakan untuk menambah *formatting* ke dalam teks dokumen. Dalam markdown, kita dapat menambahkan sintaks-sintaks yang memiliki fungsi-fungsi tertentu untuk mengubah tampilan dari teks.

# Table of Contents

- [Persiapan](#persiapan)
- [Cara Kerja Markdown](#cara-kerja-markdown)
- [Mengapa Markdown?](#mengapa-markdown)
- [Panduan Umum](#panduan-umum)
    - [Header](#header)
    - [Penekanan](#penekanan)
    - [List](#list)
        - [Berurut](#berurut)
        - [Tak Berurut](#tak-berurut)
    - [Kode Inline](#kode-inline)
    - [Link](#link)
    - [Gambar](#gambar)
    - [Blockquote](#blockquote)
- [GitHub Markdown](#github-markdown)
    - [Task List](#task-list)
    - [Tabel](#tabel)
    - [Coret Tengah](#coret-tengah)
    - [Emoji](#emoji)

## Persiapan

Untuk memulai menggunakan Markdown, kita bisa mendownload aplikasi editor, seperti ReText, ataupun menggunakan editor online seperti https://dillinger.io/.

## Cara Kerja Markdown

Editor Markdown menggunakan *Markdown processor/Parser* untuk mengkonvarsi teks Markdown ke format HTML. Setelah dikonversi, dokumen kita sudah siap untuk ditampilkan di web browser ataupun dicetak.

## Mengapa Markdown?

Markdown adalah cara mudah untuk membuat catatan, konten untuk situs web, dan dokumen siap cetak. Selain itu, Markdown juga bisa digunakan untuk buku, presentasi, hingga e-mail. Karena sintaks-sintaks yang digunakan cukup sederhana, Markdown menjadi mudah untuk dipelajari.

## Panduan Umum

### Header

Header dalam Markdown memiliki beberapa tingkat, dimana tingkat yang lebih rendah memiliki ukuran teks yang lebih kecil. Header memiliki 6 tingkat. Header dalam Markdown ditulis seperti berikut:

```
# Ini adalah Header 1 atau <h1>
## Ini adalah Header 2 atau <h2>
### Ini adalah Header 3 atau <h3>
#### Ini adalah header 4 atau <h4>
##### Ini adalah header 5 atau <h5>
###### Ini adalah header 6 atau <h6>
```

### Penekanan

Penekanan disini yaitu penulisan huruf secara **tebal** dan *miring*. Kita bisa mengganti tanda `*` dengan `_`. Kita juga bisa mengkombinasikan ***tebal dan miring***.

```
Penekanan disini yaitu penulisan huruf secara **tebal** dan *miring*. Kita bisa mengganti tanda `*` dengan `_`. Kita juga bisa mengkombinasikan ***tebal dan miring***.
```

### List

#### Berurut

```
1. Data 1
2. Data 2
3. Data 3
    1. Data 3.1
    2. Data 3.2
```

#### Tak Berurut

```
- Data 1
* Data 2
- Data 3
    - Data 3.1
    - Data 3.2
```

### Kode Inline

Cara mencetak Hello World di Python3 adalah dengan kode `print('Hello World')`.
```
Cara mencetak Hello World di Python3 adalah dengan kode `print('Hello World')`.
```

### Link

```
https://github.com/ - otomatis
[GitHub](https://github.com/)
```

### Gambar

```
Format: ![Teks](url)
Contoh: ![Logo](/data/images/logo.png)
```

### Blockquote

Untuk Quote, kita bisa menggunakan tanda `>`.

```
Seperti yang sering dia katakan,

> Aku tidak akan menyerah sampai
> kebenaran berhasil terungkap.
```

## GitHub Markdown

GitHub memiliki dukungan untuk sintaks-sintaks tambahan agar Markdown dapat terlihat lebih bagus.

### Task List

- [x] Ini adalah contoh dari Task List.
- [ ] Keren, bukan?

```
- [x] Ini adalah contoh dari Task List.
- [ ] Keren, bukan?
```

### Tabel

No|Nama
--|----
1|Revon
2|Damar

```
No|Nama
--|----
1|Revon
2|Damar
```

### Coret Tengah

Cara menampilkan daftar file dalam direktori adalah dengan command ~~rm -rf~~ ls.

```
Cara menampilkan daftar file dalam direktori adalah dengan command ~~rm -rf~~ ls.
```

### Emoji

Emoji dapat digunakan dengan sintaks `:nama_emoji:` :smile:. Berikut adalah [Cheat Sheet](https://github.com/ikatyang/emoji-cheat-sheet/blob/master/README.md) untuk emoji yang tersedia pada GitHub.
