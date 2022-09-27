# Summary
```
Minggu 1 Coding Bootcamp
Nama  : Salsabilla Pramudita
Track : FrontEnd Web Development
```
Materi :

- Unix Command Line
- Git & GitHub dasar
- HTML
- CSS
- Algoritma
- JavaScript (JS dasar & Js Conditional)


## Unix Command Line
"command line" atau "command line interface", sebenarnya yang dimaksud adalah shell yang berbasis teks
##### Shell
**Shell** merupakan user interface yang mengelola CLI dan berperan sebagai perantara yang menghubungkan user dan sistem operasi
##### Command Line Interface(CLI)
**CLI** adalah mekanisme interaksi dengan sistem operasi atau perangkat lunak komputer dengan mengetikkan perintah untuk menjalankan tugas tertentu
Cara mengakases CLI di laptop atau PC dengan sistem operasi windows dapat menekan win+R, lalu mengetikkan "cmd"

![image.png]( gambar1/xxxx.png)

**File System Structure**
FIle System adalah struktur logika yang digunakan untuk mengendalikan akses terhadap data yang ada pada harddisk
- Sebuah filesystem mengatur bagaimana data disimpan di dalam sebuah system
- Sistem operasi Windows & Unix-like menyusun file dan direktori menggunakan struktur yang bentuknya mirip tree

**Command untuk Navigasi**

| Command | fungsinya |
| ------ | ------ |
| pwd | melihat current working directory |
| ls | melihat isi sebuah directory  |
| cd | berpindah directory  |
| type/cat | melihat isi files |
| mkdir | membuat direktori |
| touch | membuat file |
| cp |menyalin file & direktori  |
| mv |untuk memindahkan atau me-rename file dan direktori   |
| rm|untuk menghapus file & direktori  |
## Git & GitHub

##### Kenapa Git dan Github tools yang wajib digunakan?
Karena kedua platform ini sangat membantu pekerjaan programmer dalam menyusun kode script secara grup/tim. Seluruh pekerjaan juga dapat dipantau dan dievaluasi dengan mudah karena penggunaan kontrol sistem.

**GIT**
Git adalah aplikasi yang dapat melacak setiap perubahan yang terjadi pada suatu folder atau file.

**GitHub**
GitHub adalah layanan cloud yang berguna untuk menyimpan dan mengelola sebuah project yang dinamakan repository.

**Perbedaan Git & GitHub**
| Git | GitHub |
| ------ | ------ |
| diakses secara offline | diakses secara online |
| di-install pada penyimpananan lokal | melalui layanan cloud |
| sebagai control version system | sebagai source code hosting |
| open source | pilihan bagi pengguna gratis dan berbayar |

**Instalasi Git**
sebelumnya download aplikasi git seperti aplikasi biasa. dilanjutkan membuat akun github.
###### Setup Awal
- **git config --global user.nama "nama"**. setelah proses instalasi git lalu ditampilkan sebuah layar terminal git bash, nah disana kita ketikkan syntax ini untuk memasukkan nama
- **git config --global user.email "nama"**. fungsi syntax ini untuk mengisikan email, perlu diingat email yang dimasukkan harus sama dengan email yang kita daftarkan pada akun github
- **git --version**, syntax ini bisa kita gunakan untuk mengecek instalasi git pada pc/laptopp kita sudah berhasil atau belum.
- **git config --list**, syntax ini berfungsi untuk mengecek apakah setup yang kita atur diawal(mengisi nama dan email) sudah berhasil atau belum.

###### Repository
- **git init namaproyek**, syntak disamping berfungsi untuk membuat repository baru.
- **git init .**, gunakan syntax ini jikalau nama folder sudah ada sebelumnya
- **git status**, digunakan untuk menlihat terjadinya perubahan atau tidak dalam folder kita
-  **git add namafile**, syntax ini untuk menambahkan file kedalam folder.
-  **git add .**, gunakan syntax ini untuk menambahkan beberapa atau semua file yang akankita masukkan kedalam folder.
-  **git commit**, Lakukan ‘git commit’ untuk save perubahan pada version control
-  **git push -u origin master** digunakan untuk mengirimkan/perubahan file ke remote repository
-  **git log**, berfungsi untuk melihat riwayat tindakan yang telah dieksekusi



## HTML
HTML adalah singkatan dari Hypertext Markup Language. HTML digunakan untuk menampilkan konten pada browser. Contoh konten yang dapat ditampilkan seperti Text, Image, Video, Link, dan masih banyak lainnya.

**Tools yang dibutuhkan untuk membuat HTML**
- **Browser**
- **Code Editor**, disini saya install Virtual Studio Code 
''' Visual Code Studio merupakan paket all in one. Kita bisa menggunakan ini untuk bahasa pemrograman apapun. Nah ada satu fitur yang disediakan oleh si VsCode ini yaitu Live Server yang mana kita tidak perlu merefresh halaman browser terhadap perubahan'''

**Struktur Html**
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Html Pertamaku</title>
</head>
<body>
    Hello saya salsa
</body>
</html>
```
**Html Element**

HTML element didefinisikan dengan 
- opening tag ```<h1>```
- content ```Judul```
- closing tag```</h1>```


##### Html Atribut
Attribute adalah properties dari sebuah HTML Element.
contohnya : didalam tag ```<h1> ``` kita tambahkan atribut ```id```, seperti code dibawah

```<h1 id="Header">Judul</h1>```


#### Tags

|Tag | Fungsinya |
| ------ | ------ |
| <p> | Membuat Pragraph |
| <h1> | Membuat Heading (h1-h9) |
| <img> | Menyisipkan gambar |
| <a>| untuk menentukan apakah link yang dituju terbuka di jendela browser saat ini, atau terbuka di jendela baru |
| <ol>| mengurutkan konten berdasarkan penomoran otomatis |
| <hr> | untuk memisahkan beberapa konten atau paragraf, membuat garis lurus secara horizontal|
| <form> | Menambahkan form|
| <Table> | Menyisipkan Tabel|

``` <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Html Pertamaku</title>
</head>
<body>
    Hello saya salsa<br>
    <table border="2">
        <thead>
            <tr>
                <td>Nama</td>
                <td>Umur</td>
            </tr>    
            <tbody>
                <tr>
                    <td>Salsa</td>
                    <td>19</td>
                </tr>
            </tbody>
        </thead>
    </table>
   
</body>
</html>```

#### Semantic Html
Semantic artinya kita menggunakan element html yang sesuai dengan kebutuhan konten
Apa kegunaan lain semantic HTML?

Meningkatkan Accessibility 
Meningkatkan SEO 
Lebih mudah di maintain

**Beberapa semantic tag yang dibawa oleh HTML5 adalah sebagai berikut:**

<article>
<aside>
<figcaption>
<figure>
<footer>
<header>
<main>
<mark>
<nav>
<section>
<summary>
<time>

