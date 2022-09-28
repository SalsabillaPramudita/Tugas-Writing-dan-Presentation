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

##### File System Structure
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
##### Html Element
HTML element didefinisikan dengan 
- opening tag ```<h1>```
- content ```Judul```
- closing tag```</h1>```

**Html Atribut**
Attribute adalah properties dari sebuah HTML Element.
contohnya : didalam tag ```<h1> ``` kita tambahkan atribut ```id```, seperti code dibawah
```<h1 id="Header">Judul</h1>```


**Tags**
|Tag | Fungsinya |
| ------ | ------ |
| p | Membuat Pragraph |
| h1 | Membuat Heading (h1-h9) |
| img | Menyisipkan gambar |
| a| untuk menentukan apakah link yang dituju terbuka di jendela browser saat ini, atau terbuka di jendela baru |
| ol| mengurutkan konten berdasarkan penomoran otomatis |
| hr | untuk memisahkan beberapa konten atau paragraf, membuat garis lurus secara horizontal|
| for> | Menambahkan form|
| Table | Menyisipkan Tabel|

**Membuat Tabel sederhana**
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
</html>
```

#### Semantic Html
Semantic artinya kita menggunakan element html yang sesuai dengan kebutuhan konten
Apa kegunaan lain semantic HTML?

Meningkatkan Accessibility 
Meningkatkan SEO 
Lebih mudah di maintain

**Beberapa semantic tag yang dibawa oleh HTML5 adalah sebagai berikut:**
```
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
```

## CSS (Cascading Style Sheets)
CSS adalah bahasa yang digunakan untuk mendesain halaman website.

Dengan CSS, kita bisa mengubah warna, menggunakan font custom, editing text format, mengatur tata letak, dan lainnya.

**3 Cara menggunakan CSS**
- **Inline Styles**, Inline styles adalah kita menambahkan CSS pada attribute element HTML ```<p style="color:aqua"; font-size:28px; ></p>```
- **Internal CSS**, CSS internal adalah CSS yang diletakkan pada bagian <head> suatu halaman HTML. Kita bisa tambahkan tag <style> di bagian <head> seperti ini
``` <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh CSS Internal</title>

    <Style>
        h1{
            background-color: azure;
            color: teal;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
    </Style>
</head>
<body>
    <h1>Halo, saya Salsa</h1>
</body>
</html>
```
- External CSS, yang dimaksud eksternal adalah kita membuat file tersendiri yang berekstensi .css. Kemudian file tersebut kita hubungkan ke dalam halaman HTML menggunakan tag <link>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contoh CSS Internal</title>
    <link rel="stylesheet" href="coba.css">
</head>
<body>
    <h1>Halo, saya Salsa</h1>

</body>
</html>
```

**Struktur CSS**
Struktur kode CSS terdiri dari tiga bagian:
- Selektor;
- Blok Deklarasi;
- Properti dan nilanya.
```
selector{
    properti1: value;
}
```
**Flexbox**
Flexbox adalah cara untuk mengatur layout. Flexbox memiliki kemampuan untuk menyesuaikan layout secara otomatis.
**Untuk Apa Flexbox?**
Tujuan dari flexbox yaitu memberikan container kemampuan untuk mengatur panjang, lebar, dan posisi item-item yang berada di dalamnya agar memaksimalkan ruang yang ada. Pengaturan ini sangat penting bagi seorang frontend developer untuk membuat sebuah website yang nyaman dilihat di berbagai device dengan berbagai macam resolusi
>> Konsepnya sederhana.
Flexbox memiliki 1 parent/container dan bisa beberapa child/item.
>>
**Property container Flexbox**
- flex-direction
Menentukkan arah (direction) yang akan diberlakukan untuk item-item yang ada pada container flexbox. 
- flex-wrap
flex-wrap digunakan untuk mendefinisikan bahwa elemen item di dalam container flexbox tidak harus disejajarkan dalam satu baris.
- flex-flow
Flex flow yaitu sebagai shortcut untuk set up flex-direction dan flex-wrap secara bersamaan
- justify-content
justify-content digunakan untuk mensejajarkan item-item diantara flexbox agar container dari flexbox tersebut bisa mendistribusikan ruang kosong yang tersisa ketika item flex dalam satu baris tersebut tidak flexsibel atau meskipun flexsibel tapi sudah mencapai batas ukuran maksimum
- align-items
align-items mendefinisikan bagaimana item-item pada container flex tersebut diletakkan sepanjang garis tegak lurus pada sumbu utama (cross-axis)
- align-content
align-content digunakan untuk mensejajarkan garis flex container ketika ada ruang kosong secara garis tegak lurus pada sumbu utama (cross-axis)

## Algoritma & Pseudocode
Algoritma adalah deskripsi berupa step-step yang dibutuhkan untuk menyelesaikan suatu masalah 
**Kualitas wajib dari Algoritma**
Input dan output harus didefinisikan terlebih dahulu dengan tepat
Setiap step harus benar-benar clear dan tidak ambigu
Algoritma seharusnya tidak mengandung suatu code pada bahasa pemograman tertentu. Algoritma harus dibuat agar dapat digunakan dalam bahasa pemograman apapun.
**Kenapa harus belajar Algoritma?**
- Programming itu adalah algoritma dan struktur data
- Data struktur digunakan untuk mengelola/manajemen sebuah data
- Dan Algoritma yang akan menyelesaikan suatu permasalahan menggunakan data tersebut.

**Contoh Algoritma dalam codingan**
```
var a,b,c;
a = prompt("masukkan number1");
b = prompt("masukkan number2");
c = Number (a) + Number (b);
console.log(c);
```

#### Pseudocode
Pseudocode adalah menuliskan algoritma dengan umumnya bahasa inggris sebelum kita implementasikan ke bahasa pemograman tertentu.

**Struktur Pseudocode**
- Judul
{Berisi Judul Algoritma}
- Deskripsi
{Berisi Deklarasi Variabel atau Konstantan}
- Implementasi
{Berisi Inti Algoritma}

Bagaimana cara menulis pseudocode?
**Panduan menulis pseudocode**
- Menggunakan HURUF BESAR pada kata kunci (key commands). 
CONTOH: IF number is > 10 THEN …
- 1 statement =  1 baris 
- Gunakan indentasi
- Please please be specific
- Tapi tetap simpel


**Contoh Psudocode**
```
program hitung_luas_segitiga

deklarasi
var luas,alas,tinggi:integer;

algoritma:
alas <– 25;
tinggi <– 30;

luas <– 1/2 * alas * tinggi

write(luas)
```

## JavaScript dasar
Javascript adalah bahasa pemograman yang sangat powerful yang digunakan untuk logic pada sebuah website
Javascript juga dapat membuat website menjadi interaktif dan dinamis

**Syntax dan Statement**
Syntax bisa dianalogikan seperti kosa kata (vocabulary) dan tata cara (grammar) pada bahasa pemograman.
Kita menggunakan syntax tertentu untuk membuat statement program, instruksi untuk djalankan/dieksekusi oleh web browser, compiler, ataupun intrepreter

**Ada tiga macam jendela dialog pada Javascript:**
Jendela dialog **alert()**;
Jendela dialog **confirm()**;
Jendela dialog **prompt()**;
Dillinger is currently extended with the following plugins.
Instructions on how to use them in your own application are linked below.

**Console Log**
Console log adalah tempat kita untuk cek logic pemograman web yang kita kembangkan

**Comments**
Comments adalah sintaks yang digunakan untuk memberi keterangan tentang suatu statement. Menggunakan bahasa inggris atau bahasa indonesia.
- Single Comments: //
- Multiline Comments: /* */

**Tipe Data (Data Types)**
Tipe data adalah klasifikasi yang kita berikan untuk berbagai macam data yang digunakan dalam programming.

Ada 6 tipe data fundamental pada Javascript
- number
Tipe data number adalah tipe data yang mengandung semua angka termasuk angka desimal.
Contoh:
2, 4, 1200, 23.42

- string
Tipe data string adalah grup karakter yang ada pada keyboard laptop/PC kita yaitu letters (huruf), number (angka), spaces (spasi), symbol, dan lainnya.
Harus diawali dan diakhiri dengan single quotes ‘ … ‘ ataupun double quotes “ … “.

- boolean
Tipe data boolean adalah tipe data yang hanya mempunyai 2 buah nilai.
2 buah nilai tersebut adalah TRUE (benar) or FALSE (salah).
Analoginya adalah seperti tombol/button ON/OFF dan juga seperti sebuah jawaban antara YES/NO.

- null
Tipe data null adalah tipe data yang diartikan bahwa sebuah variable/data tidak memiliki nilai.
Null berbeda dengan string kosong. String kosong masih memiliki tipe data string.

- undefined
Tipe data undefined adalah tipe data yang merepresentasikan varibel/data yang tidak memiliki nilai.
Undefined berbeda dengan null.
Undefined didapat dari hasil berikut:
-- Nilai dari pemanggilan variabel yang belum didefinisikan
-- Nilai dari pemanggilan element array yang tidak ada
-- Nilai dari pemanggilan property objek yang tidak ada
-- Nilai dari pemanggilan fungsi yang tidak mengembalikan nilai (return)
-- Nilai dari parameter fungsi yang tidak memiliki argumen

- object
Tipe data object adalah koleksi data yang saling berhubungan (related). Tipe data pbject dapat menyimpan data dengan tipe data apapun (number, string, boolean, dan lainnya).
Tipe data object mempunyai key dan value.

**Variabel**
variable adalah container/tempat untuk menyimpan sebuah nilai
3 hal yang dapat dilakukan pada variabel
- Membuat variabel dengan nama yang jelas dan menggambarkan tentang data tersebut
- Menyimpan dan mengupdate informasi/data yang disimpan
- Mendapatkan/menampilan data yang tersimpan

Ada 3 cara mendefinisikan sebuah variabel.
- var
    ```
    var nama = 'salsa';
    console.log(nama)
    ```
- let
   ```
    let meal = 'nagari';
    console.log(meal);//output: "nagari"

    meal = 'manggung';
    console.log(meal);//output : "manggung"
    ```
- const
-- Gunakan const jika variabel tidak dapat diubah nilainya.
-- Biasanya digunakan untuk menggambarkan konstanta sebuah nilai. Seperti konstanta pi = 3.14.
    ```
    const pi = 3.14;
    console.log(pi);//otput : 3.14

    pi = 10;
    console.log(pi);//uncaught error    
    ```
**perbedaan var dan let**
let dikenalkan pada versi javascript terbaru ES6
Variabel let mendukung kaidah global variabel dan local variabel
Jadi, dianjurkan untuk menggunak let untuk variabel yang dinamis/dapat diubah

**Operator**
- **Assignment Operator (=)**, Assignment operator digunakan untuk menyimpan sebuah nilai pada variabel
- Mathematical Assignment Operator
    ```
    let p = 10;
    p -= 2;
    console.log(p);//hasil: 8
    ```
- Increment dan Decrement
Gunakan increment atau decrement untuk menambah atau mengurangi sebesar 1 nilai.
     ```
    let p = 9;
    p++;
    console.log(p);//hasil: 10
    ```
- Arithmetic Operator
Arithmetic operator adalah operator yang melibatkan operasi matematika.
-- Tambah (+)
-- Kuramg (-)
-- Perkalian (*)
-- Pembagian (/)
-- Modulus (%)
    ```
    console.log(10*3);//hasil: 30
    ```
- Comparison Operator
-- Comparison operator adalah operator yang membandingkan satu nilai dengan nilai lainnya.
-- Hasil operasi yang melibatkan comparison operator adalah antara true or false
-- **simbol comparison**
Lebih kecil dari : <
Lebih besar dari: >
Lebih kecil atau sama dengan: <=
Lebih besar atau sama dengan: >=
Sama dengan: ===
Tidak sama dengan: !==
- Logical Operator
-- Logical operator biasa digunakan untuk sebuah CONDITIONAL pada pemograman.
-- Menghasilkan nilai BOOLEAN yaitu TRUE or FALSE.
Simbol dari Logical Operator adalah sebagai berikut:
-- AND operator : &&
-- OR operator: ||
-- NOT operator: !

## JavaScript dasar Conditional
- Conditional merupakan statement percabangan yang menggambarkan suatu kondisi
- Conditional statement akan mengecek kondisi spesifik dan menjalankan perintah berdasarkan kondisi tersebut
- Yang dicek adalah apakah kondisi tersebut TRUE (benar).
Jika TRUE maka code didalam kondisi tersebut dijalankan.

**Contoh Conditional
IF Statement**
```
let hujan = true;
if (hujan){
    console.log('bawa payung');//output: "bawa payung"
}
```
**IF … ELSE Statement**
Else akan mengeksekusi sebuah statement/code jika suatu kondisi bernilai FALSE
```
let hujan = false;
if (hujan){
    console.log('bawa payung');
}
else{
    console.log('jangan bawa payung')
}//output:"jangan bawa payung"
```
**IF .. ELSE IF Statement**
Else … If statement dapat kita gunakan jika kita mempunyai berbagai kondisi.
```
let lampulalulintas='hijau'
if (lampulalulintas == 'merah'){
    console.log('berhenti!');
}else if (lampulalulintas == 'kuning'){
    console.log('hati-hati')
}else if(lampulalulintas=='hijau'){
    console.log('jalan')
}else {
    console.log('perintah tidak diketahui')
}// output : jalan
```

**Switch Case Conditional**
Gunakan switch case jika kondisi dan percabangan terlalu banyak
```
var remotAc = 2;
switch(remotAc){
    case 1: {console.log('Hidupkan AC'); break;}
    case 2: {console.log('turunkan suhu AC'); break;}
    case 3: {console.log('naikkan suhu AC'); break;}
    case 3: {console.log('naikkan suhu AC'); break;}
    case 4: {console.log('dry mode'); break;}
    default : {console.log('tidak ada tindakan');}

}//otput : "turunkan suhu AC"
```
