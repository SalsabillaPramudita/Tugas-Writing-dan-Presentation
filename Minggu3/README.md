# Summary
```
Minggu 3 Web Development
Nama  : Salsabilla Pramudita
Track : FrontEnd Web Development
```
Materi :
- JavaScript intermediate - Array & Multidimensional Array
- JavaScript Intermediate - Object & Array of Object
- JavaScript Intermediate - Rekursif dan JavaScript Intermediate - Modules
- JavaScript Intermediate - Asynchronous - Introduction dan JavaScript Intermediate - Asynchronous - Promise
- JavaScript Intermediate - Web Storage



### Day 1 JavaScript intermediate - Array & Multidimensional Array

#### Array
Array di dalam Javascript mampu menyimpan banyak data dengan tipe data yang berbagai macam
- **Cara Membuat Array**
    ```
    let arr = ["hallo", 1, "true"]
    ```
- **Cara akses Array** 
    ```
    console.log(arr)
    ```
    berdasarkan index
    ```
    console.log(arr[1]) //output 1
    ```
- **Array Properties**
   - length\
        length berfungsi untuk menjumlahkan banyak array
    ```
    console.log(arr.length)
    ```
   - push()\
        Menambahkan elemen baru ke akhir array, dan mengembalikan panjang baru
      ```
      let arrBuah = ["jeruk","semangka", "pepaya", "rambutan"]

       arrBuah.push("durian")//
      ```
      output
      
      ![image.png]( gambar/output1.PNG)\
      bisa dilihat dari codingan dan hasilnya, di array arrBuah kita tidak menambahkan "durian", dengan push() kita bisa menambahkan data "durian", perlu diperhatikan push() hanya bisa menambahkan data diposisi akhir. 
      
   - pop()\
        Menghapus elemen terakhir dari array, dan mengembalikan elemen itu\
        ```
        arrBuah.pop()
        console.log(arrBuah)
        ```
        output
      
      ![image.png]( gambar/output2.PNG)\
      output yang dihasilkan adalah seperti gambar diatas, yang mana data "durian" yang kita push sebelumnya sudah terhapus, beginilah cara kerja pop()
        
   - unshift()        
        Menambahkan elemen baru ke awal array, dan mengembalikan panjang baru\
        ```
        arrBuah.unshift("apel")
        console.log(arrBuah)
        ```
       output
      
      ![image.png]( gambar/output3.PNG)\
      pada gambar diatas terdapat "apel", yang mana itu kita dapatkan dari properti unshift
      
   - shift()        
        Menghapus elemen pertama dari array, dan mengembalikan elemen itu
        ```
         arrBuah.shift()
         console.log(arrBuah)
        ```
      output
      
      ![image.png]( gambar/output4.PNG)\
      dari gambar diatas, element pertama sudah hilang, itu karna properti shift looh
   - splice()\
      Menambahkan/Menghapus elemen dari array
      ```
      arrBuah.splice(2, 0, "buah pisang")
      ```
      splice, merubah data arraynya dan dapat mereturn nilai
   - slice()\
        Memilih bagian dari array, dan mengembalikan array baru
      ```
      let slice = arrBuah.slice(2, 4)
      console.log(arrBuah)
      console.log(slice)      
      ```
      mengambil data dengan cara men-copy
  
 **Looping pada Array**
 
- For Of\
    JavaScript untuk pernyataan loop melalui nilai-nilai objek yang dapat diubah. Ini memungkinkan Anda mengulang struktur data yang dapat diubah seperti Array, Strings, Maps, NodeLists, dan banyak lagi
    ```
        for (variable of iterable) {
      // code block to be executed
    }    
    ```
    
    contoh 
    ```
    let arrBuah = ["jeruk","semangka", "pepaya", "rambutan"]
    
    for(let buah of arrBuah){
    console.log(buah)
    }
    ```
    
    output
    
    ![image.png]( gambar/output5.PNG)
    
  
- For Each
    
    Metode forEach() memanggil fungsi untuk setiap elemen dalam array.

    Metode forEach() tidak dijalankan untuk elemen kosong
    
    ```
    array.forEach(function(currentValue, index, arr), thisValue)    
    ```
    contoh
    ```
     let arrBuah = ["jeruk","semangka", "pepaya", "rambutan"]
      arrBuah.forEach((item) => {
      console.log(item)
    })
    ```
    output
    
    ![image.png]( gambar/output6.PNG)
    
- Map
    map() membuat array baru dari memanggil fungsi untuk setiap elemen array.

    map() memanggil fungsi sekali untuk setiap elemen dalam array.

    map() tidak menjalankan fungsi untuk elemen kosong.

    map() tidak mengubah array asli
    
    ```
    array.map(function(currentValue, index, arr), thisValue)
    ```
    contoh 
    ```
        let Buah = arrBuah.map((item, index) => {
        if(index % 2 === 0){
        return item + " "+ "segar"
        }
    })

     console.log(Buah)

    ```
    output
    
    ![image.png]( gambar/output7.PNG)\
    
    bisa dilihat dari gambar diatas map bisa mereturn array
  
**Perbedaan Looping pada array**


![image.png]( gambar/array-loop.png)\


**Contoh Kasus**
Merubah angka desimal menjadi persen

- menggunakan map
    ```
    let angkaDes = [
        0.45,
        0.23,
        0.54,
        0.65,
    ]

    let angkaPersen = angkaDes.map((item) => {
        return item * 100 + "%"

    })   
     console.log(angkaPersen)
    ```
    
- menggunakan for each
    ```
    let angkaPersenforEach= []
    angkaDes.forEach((item) => {
        angkaPersenforEach.push(item * 100 + "%")

    })
    console.log(angkaPersenforEach)

    ```
    
    Kasus seperti ini lebih baik menggunakan map
    
    output
    
    ![image.png]( gambar/output8.PNG)
    
 #### Multidimensional Array
 Multidimensional Array bisa dianalogikan dengan array of array. Ada array didalam array
 
 
 - Akses index multidimensional array
 
 ![image.png]( gambar/array-multi.PNG)
 
- contoh
  ```
      let arrMulti = [
      ["nama", "alpha"],
      ["umur", 17],
      ["kelas", "JS"],
    ]

    console.log(arrMulti[0][1]);
    console.log(arrMulti[2][1])
  ```
  output
  
  ![image.png]( gambar/output9.PNG)
  
  mengganti data array
  ```
      arrMulti[2][1] = "HTML"
    console.log(arrMulti)
  ```
  output
  
    ![image.png]( gambar/output10.PNG)
  
  
  
 ### Day 2 JavaScript Intermediate - Object & Array of Object\
 object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method)
- Properti adalah data lengkap dari sebuah object.

- Method adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.
-  contoh objek mobil dengan properti nilai dan method
    ![image.png]( gambar/day2.PNG)
    
 - membuat sebuah object
    syntax dasar
    ```
     let nama_obj = {
        key1: "value",
        key2: "value1",
     };
    ```
    contoh
     ```
       let siswa = {
        nama : "Salsa",
        umur : 19,
        hobby : "menyanyi",
        'nomor handphone' : 08987654,
     };
     console.log(siswa)
     ```
     Sama seperti tipe data sebelumnya. Object dapat diassign kedalam sebuah variabel\
     Sama seperti array, didalam object kita dapat menyimpan properti dengan tipe data apapun.\
     note :key pada object disebut juga dengan properti
     
 - Mengakses Object dan Property Object
     - membuat object nya dahulu
     ```
     let siswa = {
        nama : "Salsa",
        umur : 19,
        hobby : "menyanyi",
        'nomor handphone' : 08987654,
     };
     ```
     
     - ada 2 cara mengakses object
     **dot notation**
     ```
      console.log(siswa.nama)
     ```
     **bracket**
     ```
      console.log(siswa["hobby"])
      console.log(siswa["nomor handphone"])
     ```
- Membuat Key/Update Object
        ```
        let buku = {
            judul : "mantan jadi manten",
            penulis : "salsabilla",
            "jumlah halaman" : 212,


        }
        console.log(buku);
        
        //ada 2 cara
        //cara 1
        buku.tahun = 2022;
        buku.terjual = 1000;
        console.log(buku);   
        ```
        Output
        
         ![image.png]( gambar/otput11.PNG)
        
        
        ```
             //cara 2
        buku["penerbit"] = "gramedia";
        console.log(buku)
        ```
        Output
        
         ![image.png]( gambar/output12.PNG)
         
 - Menghapus Object
    Kita dapat menghapus properti dari object menggunakan delete operator
        
     Sebelum di delete
     ```
         let hewan = {
        nama : "kucing",
        kaki : 4,
        warna : "putih"
    }
    ```
    Output
    
      ![image.png]( gambar/output13.PNG)
    
    Setelah di delete
    ```
    delete hewan.warna;
    delete hewan.kaki;

    console.log(hewan)
    ```
    Output 
    
      ![image.png]( gambar/output14.PNG)
      
 - Method object
    Jika value yang kita masukkan pada property berupa function. Maka itu disebut method.
    
    ```
    const greeting = {
    welcome : function(){
        return "halo selamat datang"
    },
    afterpay : function () {
        return "terima kasih"

        },
    }

    console.log(greeting.welcome())
    console.log(greeting.afterpay())
    ```
    Output
    
       ![image.png]( gambar/output15.PNG)
       
- Nested Object
    Pada real application nanti kalian pasti menemukan data object yang kompleks. Object yang berasal dari turunan object lainnya
    ```
    let buku = {
    judul : "sayap sayap patah",
    tahun : 2009,
    penulis : {
        penulis1: {
            nama : "salsa",
            umur : 19,
            kota : "padang",
        },
        penulis2: { 
            nama : "dita",
            umur : 20,
            kota : "pariaman",
            },
        },

    };
    console.log(buku)
    console.log(buku.penulis.penulis1.nama)
    console.log(buku.penulis.penulis2.umur)
    ```
    Output
    
        ![image.png]( gambar/output16.PNG)
      
 - Looping Object
    Jika kita ingin menampilkan seluruh object properti. Kita bisa menggunakan looping. Jadi tidak perlu mengakses secara manual memanggil setiap propertinya
    ```
     let buku = {
    judul : "sayap sayap patah",
    tahun : 2009,
    penulis : {
        penulis1: {
            nama : "salsa",
            umur : 19,
            kota : "padang",
        },
        penulis2: { 
            nama : "dita",
            umur : 20,
            kota : "pariaman",
        },
        },

    };
    console.log(buku)

    for(let key in buku.penulis.penulis1){
        console.log(buku.penulis.penulis1[key], 'ini dari nested')
    }
    ```
    Output
    
       ![image.png]( gambar/output17.PNG)
       
 - Array of Object
     ```
     let siswa = [{
        nama : "Salsa",
        umur : 19,
        hobby : "menyanyi",
     },
     {
        nama : "adi",
        umur : 18,
        hobby : "berenang",

     },
     {
        nama : "rina",
        umur : 16,
        hobby : "rebahan",

     }];

     console.log(siswa);
     let data = siswa.map((el) => {
        // console.log(el.nama)
        el.status = 'aktif';
        return el
     })
     console.log(data)

     console.log((siswa)[0].nama)
     ```
     Output
     
       ![image.png]( gambar/output18.PNG)
       
 ### Day 3 - JavaScript Intermediate - Rekursif dan JavaScript Intermediate - Modules

**Modules**
JS Modules adalah cara untuk memisahkan kode file yang berbeda/
Keuntungan Menggunakan Modules
    - mudah untuk mengelola kode 
    - kode tidak menumpuk di 1 file
    
- Export Import
    Kita dapat melakukan export pada variabel, function, class
    
- Contoh Kasus Export Import\
    Jepang Meng-Export barang dan Indonesia import barang dari jepang.\
  Pertama yang diperlukan dalam module ini adalah menambahkan type"modul" di tag sript yang ada di file html
      ```
      <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta http-equiv="X-UA-Compatible" content="IE=edge">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
    </head>
    <body>

      <!-- file yg ada disini cuma bisa melakukan import -->
      <script src="./indonesia.js" type="module"></script>
    </body>
    </html>
      ```
      
     **jepang.js(export)**
     ```
    export let motor = ["suzuki","yamaha","honda","kawasaki"]
    export let smartphone = ["samsung","sony","fijitsu","LG"]
     ```
     
    **indonesia.js(import)**
    ```
    import {motor, smartphone} from "./jepang.js"

    console.log(smartphone)

    console.log(motor)
    ```
    Output
    
           ![image.png]( gambar/output19.PNG)
           
   Method as(alias)\
      as fungsinya merubah variabel\
      ```
      import {motor as motorJepang, smartphone} from "./jepang.js"

        console.log(smartphone)
        console.log(motorJepang)
       ```
    Export Default\
    export default cuma bisa 1 yang di export\
    export default ditangkap tnpa kurung kurawal\
    
    jepang.js
    ```
    let entertaiment = ["anime","manga","wibu","dorama"]
    export default entertaiment
    ```
    
    indonesia.js
    ```
    import entertaiment,{motor as motorJepang, smartphone} from "./jepang.js"
    console.log(entertaiment)
    ```
    contoh export function\
    jepang.js
    ```
    export function sayHello(){
    console.log("hellooo")
    }
    ```
    
    indonesia.js
    ```
    import entertaiment,{motor as motorJepang, smartphone, sayHello} from "./jepang.js"

    sayHello();
    ```
    
    Membuat Export dari file lain, dan import dilakukan di file jepang.js\
    amerika.js
    ```
    export let barang = ["macboock","iphone","iwatch"]
    ```
    
    jepang.js
    ```
    import {barang} from "./amerika.js"
    console.log(barang)
    ```
    
- Konsep Export Import
       ![image.png]( gambar/exporImpor.png)

**Recursive**
adalah function yang memanggil dirinya sendiri sampai kondisi tertentu\
Recursive kebanyakan digunakan untuk case matematika, fisika, kimia, dan yang berhubungan dengan calculation\

- Ciri dari rekursif\
 - Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti, yang berarti algoritma kita tidak benar.\
 - Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya. Hal ini penting diingat, karena tujuan utama dari rekursif ialah memecahkan masalah dengan mengurangi masalah tersebut menjadi masalah-masalah kecil.
 Function recursive punya
base case -> titik paling kecil(berhenti)
recursion case -> titik dia manggil diri dia sendiri  

- Contoh Kasus
menampilkan deret angka 1 2 3 4 5
    ```
    function deretAngka(n){
        if (n == 1) {
          console.log(n)
        } else {
          deretAngka(n-1)
          console.log(n);
        }
      }
      deretAngka(5)
    ```
    
 Mencari Nilai faktorial 5!
 
     ```
       function faktorial(n) {
        if (n == 1) {
          return 1
        } else {
          return n * faktorial(n - 1)
        }
      }
      console.log(faktorial(5))
     ```

 ### Day 4 - JavaScript Intermediate - Asynchronous - Introduction dan JavaScript Intermediate - Asynchronous - Promise
 Pada konsep asynchronous, code akan dieksekusi tanpa menunggu eksekusi code lain selesai sehingga seakan-akan dieksekusi secara bersamaan. 
Penggunaan asynchronous dapat dilakukan jika kita ingin mengambil data dari database\
Mengapa perlu menggunakan asynchronous?

Asynchronous dibutuhkan ketika ada proses yangg membutuhkan waktu lama. Jadi kita bisa mengerjakan proses yg lain secara paralel.
- Callbacks adalah suatu function namun cara pengeksekusiannya yang berbeda yaitu hanya mengeksekusi pada point tertentu.
- Salah satu function yang digunakan untuk mengatur penjadwalan asynchronous adalah setTimeout function
- contoh penggunaan asynchronous
    ```
    function a() {
        console.log('a done')
      }
        function b() {
        setTimeout(
          function() {
            console.log('b done')
          },2000
        )
      }
      function c() {
      console.log('c done')
      }
    a()
    b()
    c()
    ```
 - contoh penggunaan callback()
     ```
     console.log("CALLBACK")
    console.log("A")

    // butuh proses yg memakan waktu
    // callback -> function yg dijadikan sbg argumen
    setTimeout(() => {
      console.log("B")
    }, 1000)

    console.log("C")
     ```
- contoh penggunaan promises
    ```
    console.log("PROMISES")
    // pembuatan promise.............
    let nontonPromise = new Promise((resolve, reject) => {
      if (true) {
        resolve("nonton terpenuhi") // berhasil
      } 

      reject("gagal"); // gagal
    });

    // eksekusi proses..............
    console.log("A");

    nontonPromise
      .then((result) => {
        console.log(result);
        return `${result} bareng doi`
      })
      .then((result) => {
        console.log(result)
      })
      .catch((err) => {
        console.log(err);
      });

    console.log("C");
    ```
  - contoh penggunaan promises dari function
      ```
          console.log("PROMISES dari function")
        let nonton = (kondisi) => {
          return new Promise((resolve, reject) => {
            if (kondisi == "jalan") {
              resolve("nonton terpenuhi")
            }
            reject("batal nonton")
          })
        }

        nonton("jalan")
        .then(result => {
          console.log(result)
        })
        .catch(err => {
          console.log(err);
        })
      ```

### Day 5 - JavaScript Intermediate - Web Storage
Web Storage atau biasanya dapat diketahui sebagai DOM storage (Document Object Model Storage), adalah metode yang digunakan pada website untuk dapat menyimpan data pada sisi klien (client-side).

**Macam-macam Web Storage yang Bekerja pada Client-Side**
Terdapat beberapa web storage yang dapat anda ketahui, berikut ini macam-macam web-storage pengertian beserta dengan fungsinya :

Cache
Cache dalam web browser adalah teknologi yang diguanakan untuk menyimpan atau asset dapat berupa (data, gambar, file dan dokumen lain sebagainya) ketika website dimuat pertama kali, sehingga ketika web tersebut di-load kembali akan mejadi lebih cepat karena tidak perlu men-download kembali file-file dari server.


Cookie
Cookie adalah sebagin kecil dari data yang dikirim dari sebuah situs web dan disimpan dalam komputer pengguna oleh web browser ketika pengguna tersebut sedang membuka halaman dari suatu webiste tertentu.
Sebenarnya ketika anda menggunakan web browser sangat sering sekali bekerja dengan cookie, misalkan :
Menyimpan Login informasi pada website yang telah di akses oleh user.
Menyimpan Configurasi website misal bahasa.
Memberikan Rekomendasiberdasarkan aktivitas dari web browser dapat berupa iklan, playlist, berita dan lain sebagainya.


Session Storage
Session Storage adalah penyimpanan website pada sisi klien yang digunakan untuk menyimpan data selama web-browser atau tab yang memuat halaman suatu website belum ditutup atau keluar (close).
Session Storage dalam membangun sistem berbasis website biasanya digunakan untuk menyimpan user identity sebagai login status.
