# WEEK 6

Nama : Salsabilla Pramudita\
Track : FrontEnd Development\
Day 1 Front End Bootcamp

Materi : 
- Day 1 React.js Basic - JavaScript for React.js dan React.js Basic - Intro to React.js, Virtual DOM, and JSX
- Day 2 React.js Basic - Functional Component, React.js Basic - Props and State,  React.js Basic - Styling (CSS Stylesheet, CSS Modules & CSS-in-JS)
- Day 3 React.js Basic - Handling Events, React.js Basic - Conditional Rendering
- Day 4 React.js Basic - Forms
- Day 5 React.js Lanjutan - Lifecycle Method dan React.js Lanjutan - Hooks

### Day 1 React.js Basic - JavaScript for React.js dan Intro to React.js, Virtual DOM, and JSX
- React.Js\
  Adalah Framework view library javascript untuk membuat tampilan (user interface) pada website. React memungkinkan untuk membuat UI kompleks dari kumpulan kode yang kecil dan terisolasi yang disebut “komponen”.
  
- Kenapa menggunakan React.js?
    - Performa\
      ReactJS menggunakan kerangka VDOM yang membuat aplikasi web berjalan lebih cepat. Dengan kerangka ini, antarmuka pengguna yang kompleks dapat dipecah menjadi beberapa komponen. Dengan begitu, proses pengembangan bisa berjalan lebih cepat karena memungkinkan banyak pengguna bekerja pada komponen secara bersamaan
    
    - Modular\
      dengan React kita dapat menerapkan konsep modular Javascript pada. React JS membagi 1 tampilan website menjadi komponen-komponen kecil
      
    - Scalable\
      React JS dapat digunakan pada aplikasi berskara kecil hingga besar dan kompleks
      
    - Popular\
      Simpel adalah salah satu alasan mengapa ReactJS cukup populer di kalangan developer. Dengan pendekatan berbasis komponen serta penggunaan Javascript yang sederhana dalam pembuatan website atau aplikasi mobile, ReactJS banyak menjadi pilihan bagi para developer.

- Installl React JS
  - Download Node.js\
    link download https://nodejs.org. nodejs adalah sebuah runtime javascript yang di buat dari v8 engine-nya chrome
  - Install Node.js\
    sangat mudah dalam penginstallan node.js ini kita tinggal next saja, lalu diakhir klik finish
  - Buat Folder\
    Setelah selesai, buat folder baru untuk instalasi react
  - Tes Node.js\
    untuk memastikan Node.js kita berhasil terinstal maka bukalah cmd dan ketikkan **npm -v**
    ![img](gambar/gambar1.PNG)
  - Install React\
    install React dengan mengetik **npm install -g create-react-app**
  - Tes React\
    Untuk mengecek proses instalasinya, bisa dilakukan dengan mengetik **create-react-app –version**
  - Create Project\
    **create-react-app project-baru** (kita bisa mengganti "project-baru” dengan nama project yang lain)
     ![img](gambar/gambar2.PNG)
  - Jalankan Project\
    Setelah proses pembuatan project selesai,ketikkan\
    **cd project-baru\
      npm start**\
    akan muncul halaman web yang terbuka otomatis dengan alamat localhost:3000
    ![img](gambar/gambar3.PNG)
    
- Virtual DOM\
    Virtual DOM secara singkat nya adalah sebuah javascript object (virtual) yang merepresentasikan DOM yang sebenarnya (real DOM). karena virtual dom ini adalah representasi dari real dom maka virtual dom adalah sebuah replikasi (copy) dari real dom tersebut. Berbeda konsep dengan DOM, virtual dom ini memiliki konsep yaitu setiap saat perubahan terjadi di state pada aplikasi kita maka akan membuat virtual dom yang baru (cloning). Seperti terlihat pada gambar diatas, ketika ada perubahan maka virtual dom akan membuat virtual dom baru dan melakukan comparation (diffed) dari virtual dom sebelumnya. Hanya perubahan tersebut yang akan dikirim ke real dom untuk mengupdate nya. Proses seperti ini membuat virtual DOM lebih cepat dibandingkan dengan DOM, jadi tidak perlu adanya proses re-rendering lagi pada keseluruhan DOM

    ![img](gambar/gambar4.png)\
  Pada React, setiap bagian dari UI adalah component, dan setiap component mempunyai state. React menggunakan konsep Observable Pattern dan mengamati setiap perubahan pada state. Ketika state pada sebuah component berubah, react mengupadate virtual DOM tree. Setelah virtual DOM diperbarui, React kemudian membandingkan versi sekarang virtual DOM dengan versi sebelumnya. Setelah mengetahui object pada virtual DOM mana yang berubah maka hanya object tersebutlah yang akan dirubah pada real DOM. Proses seperti membuat performance aplikasi lebih baik
  
 - JSX\
   JSX adalah sebuah sintaks tertanam, yang seperti XML. Ini dimaksudkan untuk diubah menjadi JavaScript yang valid, meskipun semantik dari transformasi itu khusus untuk implementasi. JSX perlu di compile untuk menjadi Javascript. Jadi sebelum ditampilkan pada browser, JSX akan dicompile menjadi javascipt terlebih dahulu. Dengan **JSX kita dapat menggunakan HTML didalam file extension (.js)**
    ![img](gambar/gambar5.PNG)\
    
   Setiap JSX hanya bisa memiliki1 parent element
   ```js
   import React from "react";

    function App() {
      return (
      <p>hello world</p>
      <p>Aku Salsa</p>
      );
    }

    export default App;

   ```
   Codingan diatas akan muncul eror seperti dibawah ini
    ![img](gambar/gambar6.PNG)\
    
    Apabila kita ingin membuat 2 parent element atau lebih , maka solusinya bisa menggunakan tag elemen div dan tag fragment
    - menggunakan div
    ```js
    import React from "react";

    function App() {
      return (
      <div>
        <p>hello world</p>
        <p>Aku Salsa</p>
      </div>
      );
    }

    export default App;
    ```
    - Menggunakan tag fragment
    ```js
    import React from "react";

    function App() {
      return (
      <>
        <p>hello world</p>
        <p>Aku Salsa</p>
      </>
      );
    }

    export default App;
    ```
    maka outputnya berhasil seperti dibawah ini
     ![img](gambar/gambar7.PNG)
  
- Membuat Component\
   Component memungkinkan kita membagi User Interface (UI) menjadi bagian-bagian yang independen dan dapat digunakan kembali, dan memikirkan setiap bagian secara terpisah. Secara konseptual, komponen seperti fungsi JavaScript.\
   Component dibuat jika component tersebut bersifat reusable code. Pada skala project, buatlah component jika component tersebut dibutuhkan pada section page lain
   
   - buatlah folder baru didalam folder src\
       ![img](gambar/gambar8.jpg)
     
   - buatl file didalam components, berikan huruf besar pada awal penamaan file
      disini saya membuat file bernama Home.js. didalamnya terdapat sebuah fungsi yang mana penamaan fungsi tersebut juga diawali dengan huruf kapital
      ```js
      function Home() {
        return (
          <div>
            <h1>Home</h1>
          </div>
        )
      }

      export default Home
      ```
    - memanggil file Home.js di file App.js
       ![img](gambar/gambar9.PNG)
      
    - output
       ![img](gambar/gambar10.PNG)
       
   ### Day 2 React.js Basic - Functional Component, Props and State, Styling (CSS Stylesheet, CSS Modules & CSS-in-JS)
   
   - Contoh codingan sederhana dengan styling css
   
   file App.js
    ```js
   import './App.css';

  function App() {
  return (
    <>

  <div className="container">
      <img src='https://img.freepik.com/free-vector/illustration-female-character-wearing-hijab-working-office_10045-686.jpg?w=740&t=st=1667142531~exp=1667143131~hmac=7c13c7625279a79bf980b75e952aaa0aebc1c672693e13b2596cfd1ead7693e1'
      alt='' className='profile-img'></img>
    
          <div className='info-profile'>
            <h2>Salsa</h2>
            <h3>19 Tahun</h3>
            <p>Peserta Front End</p>
          </div>
        </div>
        </>
      );
    }

    export default App;
    ```
    
    file App.css
     ```css
      .profile-img{
    width: 150px;
    height: 150px;
    border-radius: 100%;
    overflow: hidden;
    object-fit: cover;
    }
    .info-profile{
      margin-left: 20px;

    }

    .container{
      margin-left: 100px;
      display: flex;
    }
    ```
    
    output
     ![img](gambar/gambar11.PNG)
     
     dari contoh kodingan diatas adalah contoh kasus sederhana, bagaimana kita mau menampilkan banyak data?, maka solusinya membuat component yang berisikan content data tersebut, lalu nantinya kita akan panggil dari file App.js nya.
     
     ![img](gambar/gambar12.PNG)\
        dari gambar diatas, saya sudah membuat folder components dan file MemberInfo.jsx. berikut codingan yang ada dalam file tersebut. 
      
    ```
      const MemberInfo= ()=>{
      return(        
      <div className="container">
      <img src='https://img.freepik.com/free-vector/illustration-female-character-wearing-hijab-working-office_10045-686.jpg?w=740&t=st=1667142531~exp=1667143131~hmac=7c13c7625279a79bf980b75e952aaa0aebc1c672693e13b2596cfd1ead7693e1'
      alt='' className='profile-img'></img>

          <div className='info-profile'>
              <h2>Salsa</h2>
              <h3>19 Tahun</h3>
              <p>Peserta Front End</p>
          </div>
          </div>
          )
      }
       export default MemberInfo;          
    ```
      
    codingan diatas adalah content yang kita buat pada file App.js sebelumnya. pindahkan saja codingan html yang ada App.js tadi ke MemberInfo.jsx
      
     berikut codingan App.js
     
     ```js
       import './App.css';
       import MemberInfo from './components/Memberinfo';

        function App() {
          return (
            <>
            <MemberInfo />
            </>
          );
        }

        export default App;
        
      ```      
      
 difile App.js ini kita hanya memanggil si MemberInfo.jsx yang telah kita buat tadi. part terpentingnya ada jangan lupa menyisipkan import di bagian atas codingan.
      
 output
 ![img](gambar/gambar13.PNG)
 
 jika kita mau manggil banyak data
 ```js
    import './App.css';
    import MemberInfo from './components/Memberinfo';

    function App() {
      return (
        <>
        <MemberInfo />
        <MemberInfo />
        <MemberInfo />

        </>
      );
    }

    export default App;
 ```
 
 output 
  ![img](gambar/gambar14.PNG)
 
 - membuat component yang dinamis dengan props dan state
 
 **props**\
 props merupakan argumen yang di-passing dari satu komponen ke komponen lain. Cara passing props sangatlah mudah, yaitu dengan menulisnya sebagai atribut pada elemen HTML. Props digunakan untuk melakukan komunikasi data antara komponen parent dan child.\
 
 contoh props
 
  file MemberInfo.jsx
  ```
  const MemberInfo= ({name, age, info, imgUrl})=>{

    return(        
    <div className="container">
    <img src={imgUrl} alt='' className='profile-img'></img>

    <div className='info-profile'>
        <h2>{name}</h2>
        <h3>{age}</h3>
        <p>{info}</p>
    </div>
    </div>
        )
    }
   export default MemberInfo;

  ```
  
  file App.js
  
  ```js
    import './App.css';
    import MemberInfo from './components/Memberinfo';

    function App() {
      return (
        <>
        <MemberInfo name={"aca"} age={20} info={"Siswa stupen Skilvul"} imgUrl={"https://img.freepik.com/free-vector/illustration-female-character-wearing-hijab-working-office_10045-686.jpg?w=740&t=st=1667142531~exp=1667143131~hmac=7c13c7625279a79bf980b75e952aaa0aebc1c672693e13b2596cfd1ead7693e1"} />

        <MemberInfo name={"adit"} age={21} info={"Siswa Akademi Polisi"} imgUrl={"https://cdn-icons-png.flaticon.com/512/1140/1140494.png?w=740&t=st=1667147325~exp=1667147925~hmac=eaf85ab253cf13ad7ceca6f4ae264c4be98341276c7881d8ed82e7e9083fc866"} />

        </>
      );
    }

    export default App;

  ```
  
  maka hasilnya seperti diabawah ini
    ![img](gambar/gambar15.PNG)
    
   
 contoh stylling dengan inline css
 ```
  const MemberInfo= ({name, age, info, imgUrl})=>{

      return(        
      <div className="container">
      <img src={imgUrl} alt='' className='profile-img'></img>

      <div className='info-profile'>
          <h2 style={{ color : "red" }}>{name}</h2>
          <h3>{age}</h3>
          <p>{info}</p>
      </div>
      </div>
      )
  }
      export default MemberInfo;

 ```
 
 output 
     ![img](gambar/gambar16.PNG)
     
 **useState**\
 useState di panggil dalam function component untuk menambahkan suatu state lokal. React akan menyimpan state antar render. useState memberikan dua hal: nilai state saat ini dan fungsi untuk memperbarui nilai tersebut. Anda dapat memanggil fungsi ini dari sebuah event handler atau dimanapun
    
 
  
  


