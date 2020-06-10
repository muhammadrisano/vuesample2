<template>
  <div class="about">
    <h1>Data buku</h1>
    <ul>
      <li v-for="(book, index) in books" :key="index">
        {{book.author}}
      </li>
    </ul>
  </div>
</template>
<script>
import axios from 'axios'
export default {
  name: 'About',
  data () {
    return {
      books: []
    }
  },
  mounted () {
    axios.get('http://34.204.60.85:8001/api/v1/book')
      .then((res) => {
        this.books = res.data.result
      })
  }
}
</script>
