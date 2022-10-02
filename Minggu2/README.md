# Summary
```
Minggu 2 Web Development
Nama  : Salsabilla Pramudita
Track : FrontEnd Web Development
```
Materi :
- Javascript Scope dan Function
- Type data dan Properties Method
- DOM

### Day 1 Javascript Scope dan Function
#### Scope
Scope adalah konsep dalam flow data variabel. Menentukan suatu variabel bisa diakses pada scope tertentu atau tidak.
-	**Blocks**\
Blocks adalah code yang berada didalam curly braces {}. Conditional, function, dan  looping menggunakan blocks.
-	**Global Scope**\
Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file. Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.
-	**Local Scope**\
Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditFunction adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur. Saat kita membutuhkan fitur tersebut nantinya, kita bisa kembali menggunakannya.
ional, dan looping. Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.

#### Function
Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur. Saat kita membutuhkan fitur tersebut nantinya, kita bisa kembali menggunakannya.

- **Struktur Fungsi**

![image.png]( gambar/struktur-fungsi.PNG)
```
\\contoh kodingan
function gretting(){
    return 'hello salsa'
}
```
- **Memanggil Function**
```
gretting()
console.log(gretting()); //output : "hello salsa"
```

- **Paramater**\
Dengan parameter, function dapat menerima sebuah inputan data dan menggunakannya untuk melakukan task/tugas.
Saat membuat function/fitur, kita harus tahu data-data yang dibutuhkan. Misalnya saat membuat function penambahan 2 buah nilai. Data yang dibutuhkan adalah 2 buah nilai tersebut.
```
function penambahan(a, b){
    return a + b;
}
```

- **Argumen**\
Argumen adalah nilai yang digunakan saat memanggil function.
Jumlah argumen harus sama dengan jumlah parameternya
Jadi jika di function penambahan ada 2 parameter nilai saat membuat function. Saat memanggil function kita gunakan 2 buah nilai argumen.  saat kita mengembangkan aplikasi dengan skala besar, function sangat sangat dibutuhkan agar kita dapat dengan mudah memanage code dan tracing code jika ada error.
```
function penambahan(a, b){
    return a + b;
}
console.log(penambahan(2,5));//output: 7
```
-	**Default Parameters**\
Default paramaters digunakan untuk memberikan nilai awal/default pada parameter function. Default parameters bisa digunakan jika kita ingin menjaga function agar tidak error saat dipanggil tanpa argumen
-	**Function Helper**\
Kita bisa menggunakan function yang sudah dibuat pada function lain.
-	**Arrow Function**\
Arrow function adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version)

- **Contoh Kasus**\
"Mencari Angka"
```
function cariAngka(x){
    let isKetemu= false
    let i = 1
    for(i; i<=20; i++){
        if(i == x){
            console.log(i, 'yes ketemu');
            isKetemu = true
        }
    }
        if(!isKetemu){
            console.log('data tidak ditemukan')
        
    }
}
cariAngka(14)
cariAngka(3)
cariAngka(23)
```
**output**

![image.PNG](gambar/OutputContohKasus.PNG)

dari output yang dikeluuarkan dari codingan kasus yang kita buat dapat dilihat bahwa angka 14 dan 3 output nya "yes ketemu", sementara angka 23 outputnya "data tidak ditemukan". Mengapa demikian?, Karena di codingan kita membuat batas loopingnya(isKetemu)adalah 20, yang artinya perulangan akan berhenti diangka 20, dan maka dari itu angka 23 tidak dapat ditemukan ini diperoleh karna kita memberikan else pada kodingan.
**Contoh Kasus**
```
function nama(a){
    console.log(`halo apa kabar ${a}?`);   

}
nama("Salsa")
```
**output**

![image.PNG](gambar/OutputContohKasus2.PNG)
