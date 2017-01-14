<template>
<div id="app" class="container">
    <div class="page-header">
        <h1>Vue.js 2 && Firebase</h1>
    </div>
    <div class="panel panel-default">
        <div class="panel-heading">
            <h3>URL Lists</h3>
        </div>
        <div class="panel-body">
            <table class="table table-striped">
                <thead>
                    <tr>
                        <th>Title</th>
                        <th>Author</th>
                        <th></th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="book in books">
                        <td>
                            <a :href="book.url">{{book.title}}</a>
                        </td>
                        <td>{{ book.author }}</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
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

let app = Firebase.initializeApp(config)
let db = app.database()

let booksRef = db.ref('books')


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
  color: #2c3e50;
  margin-top: 60px;
}
</style>
