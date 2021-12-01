<template>
  <div>
    <ul>
      <li v-for="movie,i in  movies" :key="i">{{movie.title}}</li>
    </ul>
  </div>
</template>

<script>
import Axios from 'axios'

export default {
  name: 'Mymain',
  data() {
  return {
    movies: [],
  }
},
created() {
  this.getmovies()
},
methods: {
  getmovies() {
    Axios
    // ${this.query}
      .get(`https://api.themoviedb.org/3/search/movie?api_key=8792919fa773df65448b9f5dc7714686&language=it-US&query=spiderman`)
      .then((lista) => {
        this.movies = lista.data.results
        })
  }
}
}



</script>

<style scoped lang="scss">

</style>
