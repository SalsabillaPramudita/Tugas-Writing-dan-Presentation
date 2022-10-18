```
Minggu ke 4 
Nama : Salsabilla Pramudita
Track : FrontEnd Web Development
```

Materi : 
- JavaScript Intermediate - Asynchronous - Fetch dan JavaScript Intermdiate - Asynchronous - Async Await
- Git & Github Lanjutan
- Responsive Web Design dan Bootstrap 5


### Day 1 JavaScript Intermediate - Asynchronous - Fetch dan JavaScript Intermdiate - Asynchronous - Async Await

![image.png]( gambar/img1.png)\
Dari gambar diatas, disini terjadinya proses kolaborasi antar frontEnd dan BackEnd, yang mana di sisi frontEnd itu meminta data ke Server, server meminta data ke Database. dan selanjutnyasi Database(tempat berkumpulnya semua data) mengirim data ke server, lalu server yang akan meneruskan ke frontend(app). disini kita butuh API sebagai perantara. dan biasanya data nya itu bertipe data JSON\
- API\
  API  atau application programming interface adalah sebuah interface yang bisa menghubungkan dua atau lebih aplikasi secara bersamaan dan membuat pemrograman jauh lebih mudah.
- JSON\
  JSON singkatan dari JavaScript Object Notation, adalah suatu format ringkas pertukaran data komputer. bentuk JSON ini sama seperti object tetapi ada tanda kutip diantaranya
    ```js
    {
  "employees":[
    {"firstName":"John", "lastName":"Doe"},
    {"firstName":"Anna", "lastName":"Smith"},
    {"firstName":"Peter", "lastName":"Jones"}
  ]
  }
  ```
- membuat object promise
    ```js
        ```js
        let makan = (kondisi) => {
          return new Promise((resolve, reject) => {
            if (kondisi == "lapar") {
              resolve("ayo makan")
            }
            reject("tidur")
          })
        }
    ```
- Contoh menangkap object dengan Promise

    // //contoh promise
    makan("lapar").then(result => {
      console.log(result)
    }).catch(err => {
      console.log(err)
    })
    ```
 - contoh menangkap object dengan Asyncrounous await di Javascripts
    ```js
     async function asyncMakan() {
      let result = await makan("lapar")
      console.log(result)

    }
    ```
    pada codingan diaatas await bisa jalan karna adanya function async
 - contoh async await jika ada kondisi
     ```js
     async function asyncMakan() {
      try{
        let result = await makan()
        console.log(result)  
      } catch (error) {
        console.log(error)
      }
      }
     ```  
  
- Asyncronous fetch di Javascript\
  Fetch API adalah alat default untuk membuat jaringan dalam aplikasi web. Meskipun umumnya mudah digunakan, ada beberapa nuansa yang harus diperhatikan. Fetch API pada javascript merupakan kegiatan untuk meminta/request layanan ke endpoint/letak url yang akan menerima request pada website secara local maupun public, untuk mengambil response resource / sumber daya berupa data berformat json atau text yang biasa dilakukan programmer untuk membangun website yang membutuhkan data dari website lain.
    ```js
   fetch('http://www.omdbapi.com/?apike=7dbd864d&s=john')
    console.log( dataApi )
    ```
 codingan diatas hasilnya adalah “promise”, supaya kita dapatkan data JSON yang kita mau, kita bisa tambahkan “then” 
   ```js
    fetch('http://www.omdbapi.com/?apikey=7dbd864d&s=john')
    .then(result => {return result.json()})
    .then(result => {console.log(result)});
   ```
 ![image.png]( gambar/img2.PNG)\
 maka hasilnya seperti gambar diatas.
 
 menggunakan async await
   ```js
   let getDataOmdb = async() => {
    let response = await fetch("http://www.omdbapi.com/?apikey=7dbd864d&s=john")
    let result = await response.json()
    console.log(result)
  }
  getDataOmdb()
   ```
   
  - contoh mengambil data API Digimon
    - codingan html
     ```html
      <!DOCTYPE html>
      <html lang="en">
      <head>
          <meta charset="UTF-8">
          <meta http-equiv="X-UA-Compatible" content="IE=edge">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <title>Document</title>
          <script src="script.js" defer></script>
      </head>
      <body>

          <div id="list-digimon">
          </div>


      </body>
      </html>
     ```
    - codingan js
    ```js
    containerDigimon = document.getElementById("list-digimon")

    let getDataDigimon = async() => {
      let URL = "https://digimon-api.vercel.app/api/digimon"
      let response = await fetch(URL)
      let digimon = await response.json()

    digimon.forEach(item => {
        console.log(item)
        containerDigimon.innerHTML +=
          `<div>
          <img src="${item.img}" alt="" width="200">
          <h3>${item.name}</h3>
          </div>`
      });


    }
    getDataDigimon()
    
    ```
 
**Day 2 Git & Github Lanjutan**
**Day 3  Responsive Web Design dan Bootstrap 5**

