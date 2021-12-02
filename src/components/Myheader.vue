<template>
  <div>
    <input type="text" placeholder="cerca" v-model="query">
    <button @click.prevent="getmovies">cerca</button>
  </div>
</template>

<script>
import Axios from 'axios'
export default {
  name: 'Myheader',
  data() {
  return {
    query: "",
    movies: [],
    series:[]
  }
},
methods:{

getmovies() {
    Axios
    // ${this.query}
      .get(`https://api.themoviedb.org/3/search/movie?api_key=8792919fa773df65448b9f5dc7714686&language=it-US&query=${this.query}`)
      .then((lista) => {
        this.movies = lista.data.results,
        this.$emit("search", this.movies)
        }),

    Axios
      .get(`https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=${this.query}`)
      .then((lista) => {
        this.series = lista.data.results,
        this.$emit("searchtv", this.series)
        console.log(this.series);
        })
  }
}
}

</script>

<style scoped lang="scss">

</style>