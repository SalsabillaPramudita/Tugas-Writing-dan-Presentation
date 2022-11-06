# WEEK 7

Nama : Salsabilla Pramudita\
Track : FrontEnd Development\
Week 2 Front End Bootcamp

Materi : 
- Day 1 React. JS Lanjutan - Proptypes


### Day 1 React. JS Lanjutan - Proptypes
 PropTypes merupakan library untuk menvalidasi props. Ini sangat membantu dalam meminimalkan bugs saat mengembangkan App besar. Jika props tidak benar type nya maka akan muncul warning.
 
 - Install PropTypes
    ```
    npm install prop-types
    ```
    
    ![img](gambar/gambar1.PNG)
    
  - contoh bug
  
  disini saya membuat folder component dengan file bernama StudentInfo.jsx.
  
   ```js
      const StudentInfo= ({name, age})=> {
        return(
            <>
            <h1>Hallo, aku Salsa</h1>

            <h2>{name}</h2>
            <h2>{age+2}</h2>
            </>
        )
    }
    
   ```
    
        
 file app.jsx
    
   ```js
     import StudentInfo from "./components/StudentInfo"
     import React from "react";

     function App() {

       return (
         <>
           <h1>PropTypes</h1>
           <StudentInfo name={"salsa"} age={"19"} />
         </>

       )
     }

     export default App
  ```
    
  output 
  ![img](gambar/gambar2.PNG)
    
dari codingan di file app.jsx saya memberikan age dengan tipe data string, yang mana itu tidak sesuai dengan expectasi yang telah saya buat di file StudentInfo. saya menginginkan age tersebut bertipe data number. dan hasil nya seperti output diatas yang mana tidak ada pesan eror yang memberitahu kita. maka disinilah fungsi PropTypes. PropTypes berfungsi sebagai TextChecking yang mengvalidasi tipe data kita benar atau salah.


  
