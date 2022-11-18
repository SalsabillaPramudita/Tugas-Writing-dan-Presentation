Nama : Salsabilla Pramudita\
Track : Front End Web Development\
Week 3 Front End Bootcamp\

Materi : 
- Day 1 React-js Context
- Day 2 React-js Context-lanjutan
- Day 3 React-js Testing


### Day 1 React-js Context
React Context  memungkinkan kita kirim state dari parent ke child, di manapun dia berada, tanpa repot-repot bikin rantai props.

- Kapan harus menggunakan context
  direkomendasikan menggunakan context ini jika kita mempunyai aplikasi dengan skala kecil ke menengah untuk membuat aplikasi yang kita buat mudah di kembangkan dan mudah di mengerti oleh orang-orang.

- Membuat Context
  
  ```js
  const MyContext = React.createContext(defaultValue);
  ```

Buat objek Context. Ketika React render komponen yang menerima objek Context ini akan membaca nilai context saat ini dari pencocokan terdekat Provider di atasnya dalam diagram.

Argumen defaultValue hanya digunakan ketika komponen tidak memiliki Provider yang cocok di atasnya dalam diagram. Ini dapat membantu untuk testing komponen secara terpisah tanpa membungkusnya.

- membuat Context.Provider
  ```js
  <MyContext.Provider value={/* beberapa nilai */}>
  ```

Setiap objek Context dilengkapi dengan komponen Provider React yang memungkinkan komponen consumer untuk menerima perubahan context.

Menerima prop value untuk dioper ke komponen consumer yang merupakan child Provider ini. Satu Provider dapat dihubungkan ke banyak consumer. Provider dapat disarangkan untuk override nilai lebih dalam di dalam diagram.

Semua consumer yang merupakan child Provider akan render ulang setiap kali prop value dalam Provider berubah. Perambatan dari Provider ke consumer turunannya (termasuk .contextType dan useContext) tidak sesuai ke method shouldComponentUpdate, sehingga consumer diperbarui bahkan ketika komponen lama mengupdate pembaruan tersebut.

- membuat Class.contextType
  ```js
    class MyClass extends React.Component {
      componentDidMount() {
        let value = this.context;
        /* melakukan efek samping saat *mount* menggunakan nilai MyContext */
      }
      componentDidUpdate() {
        let value = this.context;
        /* ... */
      }
      componentWillUnmount() {
        let value = this.context;
        /* ... */
      }
      render() {
        let value = this.context;
        /* *render* sesuatu berdasarkan nilai dari MyContext */
      }
    }
    MyClass.contextType = MyContext;
  ```
  Properti contextType pada kelas dapat diberikan objek Context yang dibuat oleh React.createContext(). Ini memungkinkan Anda menggunakan nilai saat ini terdekat dari tipe Context menggunakan this.context. Anda dapat merujuk ini dalam salah satu method lifecycle termasuk fungsi render.
  
  - membuat Context.Consumer
    ```js
    <MyContext.Consumer>
    {value => /* render sesuatu berdasarkan nilai *context*-nya */}
  </MyContext.Consumer>
    ```
    
    Komponen React yang menerima perubahan context. Ini memungkinkan Anda menerima context di dalam komponen fungsi.
    
Dibutuhkan sebuah fungsi sebagai child. Fungsi menerima nilai context saat ini dan mengembalikkan node React. Argumen value yang diteruskan ke fungsi akan sama dengan prop value dari Provider terdekat untuk context ini di atas dalam diagram. Jika tidak ada Provider untuk context ini di atas, argumen value akan sama dengan defaultValue yang diteruskan ke createContext().

- membuat Context.displayName
Objek Context menerima properti string displayName. React Dev menggunakan string ini untuk menentukan apa yang harus di tampilkan untuk context tersebut.

Misalnya, komponen berikut ini akan muncul sebagai MyDisplayName di Dev:

  ```js 
  const MyContext = React.createContext(/* beberapa nilai */);
  MyContext.displayName = 'MyDisplayName';

  <MyContext.Provider> // "MyDisplayName.Provider" in Dev
  <MyContext.Consumer> // "MyDisplayName.Consumer" in Dev
  ```
  
 - contoh context du functional components
 
 file thingsContext.js
   ```js
    import React from 'react'
    const ThingsContext = React.createContext({})
    export const ThingsProvider = ThingsContext.Provider
    export default ThingsContext
    ```
    
  file komponen InfoContainer
  ```js
  import React from 'react'
  import ListContainer from './ListContainer'
  import GraphContainer from './GraphContainer'
  import { ThingsProvider } from '../thingsContext'
  const InfoContainer = props => {
      // pretend we are fetching these 'things'
      const things = [
          {id: 1, name: 'thing 1', length: 5},
          {id: 2, name: 'thing 2', length: 2},
          {id: 3, name: 'thing 3', length: 6},
          {id: 4, name: 'thing 4', length: 10},
          {id: 5, name: 'thing 5', length: 1}
        ]
  return(
          <div>
              <ThingsProvider value={things}>
                  <ListContainer/>
                  <GraphContainer/>
              </ThingsProvider>
          </div>
   )
  }
  export default InfoContainer
  ```
  
  file ListDisplay
  ```js
  import React, { useContext } from 'react'
  import ThingsContext from '../thingsContext'
  import ListItem from '../components/ListItem'
  const ListDisplay = props => {
     const things = useContext(ThingsContext)
     const renderThings = things => {
       return things.map( thing => {
           return <ListItem key={thing.id} thing={thing}/>
       })
     }
   return(
          <ul>
              {renderThings(things)}
          </ul>
      )
  }
  export default ListDisplay
  ```
  
  Bagian penting di sini adalah useContext Hook. Kita mengimpor ThingsContext dan meneruskannya ke useContext Hook, menyimpannya sebagai variabel. Kita dapat  memiliki akses ke data yang dibutuhkan dan data itu juga dapat diakses oleh komponen lain. dan juga melewatkan komponen ListContainer sama sekali dan tidak perlu menurunkan apa pun! Sangat gampang bukan
  
  
  
