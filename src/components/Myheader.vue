<template>
  <div id="bg-black">
    <div id="container">
      <div id="titolo">BOOLFIX</div>
      <div>
        <input type="text" placeholder="cerca" v-model="query">
        <button @click.prevent="getmovies">cerca</button>
      </div>
      
    </div>
    
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
// w342 dimensioni dell'img
    Axios
      .get(`https://api.themoviedb.org/3/search/tv?api_key=e99307154c6dfb0b4750f6603256716d&language=it_IT&query=${this.query}`)
      .then((lista) => {
        this.series = lista.data.results,
        this.$emit("searchtv", this.series)
        })
  }
}
}

</script>

<style scoped lang="scss">
#bg-black {
  height: 100PX;
  background-color: black;
  #container{
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 90%;
    margin: 0 auto;
    #titolo{
      color: red;
      font-size: 30px;
    }
  }
}
</style>