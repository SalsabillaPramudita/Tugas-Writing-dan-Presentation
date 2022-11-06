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
  
    ```
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
    
    ```
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
    
    dari codingan di file StudentInfo saya meng
  
