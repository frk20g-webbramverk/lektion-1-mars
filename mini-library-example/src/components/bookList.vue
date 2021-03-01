<template>
    <div>
        <main class="dark" v-if="moreInfo">
            <book-info v-bind:book="moreInfo" v-on:close-book-info="close"></book-info>
        </main>
        <main class="books" v-else>
            <book v-for="(book, index) in books" v-bind:key="index" 
            v-bind:book="book" v-on:show-book="showInfo"/>
        </main>
    </div>
</template>

<script>
import book from '../components/book';
import bookInfo from './bookInfo';

export default {
    name: 'book-list',
    components: {
        book,
        bookInfo
    },
    props: {
        books: Array
    },
    data() {
        return {
            moreInfo: ''
        }
    },
    methods: {
        showInfo: function(bookToShow) {
            console.log('[bookList] Vald bok: ', bookToShow);
            this.moreInfo = bookToShow;
        },
        close: function() {
            this.moreInfo = '';
        }
    }
}
</script>

<style>
    .books {
        display: grid;
        gap: 1rem;
        grid-template-columns: repeat(4, 1fr);
    }

    .dark {
        height: 100vh;
        width: 100vw;
        background: #222;
        display: flex;
        justify-content: center;
        align-items: center;
    }
</style>