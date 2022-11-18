Nama : Salsabilla Pramudita\
Track : Front End Web Development\
Week 3 Front End Bootcamp\

Materi : 
- Day 1 React-js Context
- Day 2 React-js Context lanjutan
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
  
### - Day 2 React-js Context lanjutan

contoh kasus TodoList
- membuat component dan file
  Pertama-tama saya akan memubat folder didalam folder src, saya akan menamakan folder tersebut context.
  
Di dalam context folder ini, kita akan membuat beberapa file di dalamnya. saya hanya akan membuat satu file yang dinamai TodoContext.js. 
  ```js
  import { createContext } from "react"

  export default createContext()
  ```
- Membuat Types
  apa types itu? Di kasus yang kita hadapi, types ini berfungsi untuk mendefinisikan apa saja yang akan dilakukan oleh aplikasi kita? Seperti “Hey, aku mau mengambil data nih dari API ini, panggil type ini aja”.
  
  TodoTypes.js.
  ```js
    /**
   * @description   Types is just for constant that for dispatching our action in order to reducing a Misspelling
   */

  export const GET_TODOS = "GET_TODOS"
  export const SET_TODO_TITLE = "SET_TODO_TITLE"
  export const CLEAR_TODO_TITLE = "CLEAR_TODO_TITLE"
  export const CREATE_TODO = "CREATE_TODO"
  export const DELETE_TODO = "DELETE_TODO"
  ```
  
  -  Membuat Reducer
  Masih di dalam context folder, Saya akan membuat file yang dinamakan TodoReducer.js. Berikut kodenya.
  ```js
  import {
  SET_TODO_TITLE,
  GET_TODOS,
  CREATE_TODO,
  DELETE_TODO,
  CLEAR_TODO_TITLE
  } from "./TodoTypes"

  export default (state, { type, payload }) => {
    switch (type) {
       
      case GET_TODOS:
        return {
          ...state,
          loading: false,
          todos: payload
        }
     
      case SET_TODO_TITLE:
        return {
          ...state,
          title: payload
        }
     
      case CREATE_TODO:
        return {
          ...state,
          todos: [payload, ...state.todos]
        }
       
      case CLEAR_TODO_TITLE:
        return {
          ...state,
          title: ""
        }
     
      case DELETE_TODO:
        return {
          ...state,
          todos: state.todos.filter((todo) => todo.id !== payload)
        }
      default:
        return state
    }
  }
  ```
  
  - Membuat State
  
  TodoState.js
  ```js
  import React, { useReducer } from "react"


  import TodoContext from "./TodoContext"


  import TodoReducer from "./TodoReducer"


  import {
    SET_TODO_TITLE,
    GET_TODOS,
    CREATE_TODO,
    DELETE_TODO,
    CLEAR_TODO_TITLE
  } from "./TodoTypes"

  const TodoState = ({ children }) => {

    const initialState = {
      todos: [],
      title: "",
      loading: true
    }
    const [state, dispatch] = useReducer(TodoReducer, initialState)

  
    const setTodoTitle = (payload) => {
      dispatch({ type: SET_TODO_TITLE, payload })
    }

    // Get todos
    const getTodos = async () => {
      try {
        const todos = await fetch(
          "https://jsonplaceholder.typicode.com/todos?_limit=5"
        )
        const toJSON = await todos.json()

        dispatch({ type: GET_TODOS, payload: toJSON })
      } catch (err) {
        console.error(err.message)
      }
    }

    // Create todo
    const createTodo = async (title) => {
      const newTodo = {
        title,
        completed: false
      }

      try {
        const todo = await fetch("https://jsonplaceholder.typicode.com/todos", {
          method: "POST",
          headers: {
            "Content-Type": "application/json"
          },
          body: JSON.stringify(newTodo)
        })
        const toJSON = await todo.json()

        dispatch({ type: CLEAR_TODO_TITLE })
        dispatch({ type: CREATE_TODO, payload: toJSON })
      } catch (err) {
        console.error(err.message)
      }
    }

    // Delete Todo
    const deleteTodo = async (id) => {
      try {
        await fetch(`https://jsonplaceholder.typicode.com/todos/${id}`, {
          method: "DELETE"
        })

        dispatch({ type: DELETE_TODO, payload: id })
      } catch (err) {
        console.error(err.message)
      }
    }

 
    const { todos, title, loading } = state


    return (
      <TodoContext.Provider
        value={{
          todos,
          title,
          loading,
          getTodos,
          setTodoTitle,
          createTodo,
          deleteTodo
        }}
      >
        {children}
      </TodoContext.Provider>
    )
  }

  export default TodoState
  ```
Kode di atas sudah saya selesaikan untuk menampung keseluruhan fitur di aplikasi yang kita buat ini. State ini digunakan untuk mendeklarasikan state-state yang akan kita gunakan, fungsi-fungsi yang beritenraksi dengan server, dan beberapa logic untuk aplikasi ini

- membuat style untuk komonen
- membuat form
  ```js
  
  import React, { useContext } from "react"

  // Context
  import TodoContext from "../context/TodoContext"

  const TodoForm = () => {
    const { setTodoTitle, createTodo, title } = useContext(TodoContext)

    const onCreateTodo = (e) => {
      e.preventDefault()

      if (title === "") {
        alert("Fill the form")
        return
      }

      createTodo(title)
    }

    return (
      <form
        className='flex justify-center items-center mt-4'
        onSubmit={onCreateTodo}
      >
        <input
          type='text'
          name='title'
          className='input'
          onChange={(e) => setTodoTitle(e.target.value)}
          value={title}
          placeholder='Things you wanna do...'
        />
        <button type='submit' className='btn'>
          Save
        </button>
      </form>
    )
  }

  export default TodoForm
  ```
  
  - App.js
  ```js
  import React from "react"

  // Styles
  import "./style.css"

  // Components
  import TodoForm from "./components/TodoForm"
  import TodoList from "./components/TodoList"

  // State
  import TodoState from "./context/TodoState"

  const App = () => {
    return (
    
      <TodoState>
        <div className='container flex flex-col mt-4'>
          <h1 className='text-center'>Todo App With Context</h1>

          {/* Todo Form */}
          <TodoForm />

          {/* Todo List */}
          <div className='flex flex-col mt-4'>
            <TodoList />
          </div>
        </div>
      </TodoState>
    )
  }

  export default App
  ```
  
  ###  Day 3 React-js Testing
Apa itu react testing?

React Testing Library adalah seperangkat helpers yang memungkinkan Anda mengetes komponen pada React tanpa bergantung pada detail implementasinya.

- Jest
Jest adalah kerangka pengujian yang memerlukan konfigurasi nol dan karenanya mudah disiapkan. Jest juga lebih cepat daripada yang lain karena menggunakan teknik cerdik untuk memparalelkan uji coba lintas pekerja. Selain itu, setiap tes berjalan di lingkungan sandbox untuk menghindari konflik antara dua tes berurutan.

- install jest
  ```
  npm install --save-dev react-test-renderer
  ```
  
  - Menguji Komponen React 
  ```js
  import React from 'react';
  import ReactTestUtils from 'react-dom/test-utils'; 
  import ProductsList from '../ProductsList';

  describe('ProductHeader Component', () => {
 
    it('has an h2 tag', () => {
     //Test here
    });
   
    it('is wrapped inside a title class', () => {
     //Test here
    })
  })
  ```
  
  Untuk memeriksa keberadaan node h2, pertama-tama kita harus membuat elemen React kita menjadi sebuah node DOM di dokumen. Anda dapat melakukannya dengan bantuan beberapa API yang diekspor oleh ReactTestUtils. Misalnya, untuk membuat komponen <ProductHeader>kita, Anda dapat melakukan sesuatu seperti ini:

```js
 const component = ReactTestUtils.renderIntoDocument(<ProductHeader/>);
```
  
  Kemudian, Anda dapat mengekstrak tag h2 dari komponen dengan bantuan findRenderedDOMComponentWithTag ('tag-name'). Memeriksa semua node anak dan menemukan node yang sesuai tag-name.
 
  ```js
     it('has an h2 tag', () => {

      const component = ReactTestUtils.renderIntoDocument(<ProductHeader/>);    
      var h2 = ReactTestUtils.findRenderedDOMComponentWithTag(
       component, 'h2'
     );

  });
  ```
  
  
  Coba simpan, dan test runner Anda harus menunjukkan kepada Anda bahwa tes telah berlalu. Ini agak mengejutkan karena kita tidak memiliki pernyataan expect() seperti pada contoh sebelumnya. Sebagian besar metode yang diekspor oleh ReactTestUtils memiliki harapan yang tertanam di dalamnya. Dalam kasus khusus ini, jika utilitas uji gagal menemukan tag h2, itu akan melemparkan kesalahan dan pengujian akan gagal secara otomatis.

Sekarang, coba buat kode untuk tes kedua. Anda dapat menggunakan findRenderedDOMcomponentWithClass() untuk memeriksa apakah ada setiap node dengan kelas 'title'.
  
  ```js
      it('has a title class', () => {

      const component = ReactTestUtils.renderIntoDocument(<ProductHeader/>);    
      var node = ReactTestUtils.findRenderedDOMComponentWithClass(
       component, 'title'
     );
    })
  ```
  Jika semua berjalan dengan baik, kita akan melihat hasilnya dalam warna hijau.
