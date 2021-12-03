<template>
  <div>
    <ul>
      <li v-for="movie,i in  details" :key="i">
        <img v-if="movie.poster_path === null" src="https://i.pinimg.com/564x/01/e1/35/01e135a5bcabe81ce279076de8dfbfd9.jpg" alt="">
        <img v-else :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="">
        <div>{{movie.title}}</div>
        <div>{{movie.original_title}}</div>
        <div class="bandiera-lingua" v-if="movie.original_language === 'en'"><img :src="require('@/assets/bandiera-inglese.jpg')" alt="bandiera inglese"></div>
        <div class="bandiera-lingua" v-else-if="movie.original_language === 'it'"><img :src="require('@/assets/bandiera-italiana.jpg')" alt="bandiera italiana"></div>
        <div class="bandiera-lingua" v-else><img :src="require('@/assets/bandiera-lgbt.jpg')" alt="bandiera lgbt"></div>
        <div>{{createvote(movie.vote_average)}}</div>
      </li>
      <li v-for="serie in  detailstv" :key="serie.id">
        <img v-if="serie.poster_path === null" src="https://i.pinimg.com/564x/01/e1/35/01e135a5bcabe81ce279076de8dfbfd9.jpg" alt="">
        <img v-else :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
        <div>{{serie.name}}</div>
        <div>{{serie.original_name}}</div>
        <div class="bandiera-lingua" v-if="serie.original_language === 'en'"><img :src="require('@/assets/bandiera-inglese.jpg')" alt="bandiera inglese"></div>
        <div class="bandiera-lingua" v-else-if="serie.original_language === 'it'"><img :src="require('@/assets/bandiera-italiana.jpg')" alt="bandiera italiana"></div>
        <div class="bandiera-lingua" v-else><img :src="require('@/assets/bandiera-lgbt.jpg')" alt="bandiera lgbt"></div>
        <div>{{createvote(serie.vote_average)}}</div>
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'Mymain',
  data() {
    return {
  }},
  props:{
    details:Array,
    detailstv: Array
  },
  created() {

},
methods:{
  createvote(voto){
  return Math.floor(voto/2)
  }
}
}



</script>

<style scoped lang="scss">
.bandiera-lingua {
height: 20px;
img {
  max-height: 100%;
  width: auto;
}
}
</style>
