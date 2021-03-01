<template>
  <div id="app">
    <BooksList v-bind:books="books" />
  </div>
</template>

<script>
import books from './assets/childrensbooks.json';
import BooksList from './components/bookList';

export default {
    components: {
        BooksList
    },
    computed: {
        books() {
            return books.books;
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
