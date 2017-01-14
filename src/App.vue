<template>
  <div id="app">

  </div>
</template>

<script>
import Hello from './components/Hello'

import Firebase from 'firebase'

let config = {
    apiKey: "AIzaSyDt2Aj2IldPkN4uN91-NaN3pLgj8_Fn7xY",
    authDomain: "vuejs-books.firebaseapp.com",
    databaseURL: "https://vuejs-books.firebaseio.com",
    storageBucket: "vuejs-books.appspot.com",
    messagingSenderId: "622931788272"
}

let app = Firebase.initalizeApp(config)
let db = app.database()

let bookRef = db.ref('books')


export default {
    name: 'app',
    firebase: {
        books: booksRef
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
