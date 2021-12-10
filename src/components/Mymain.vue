<template>
  <div id="gray-bg">
    <div id="container-posters">
        <ul>
          <li v-for="movie in  details" :key="movie.id">
            <div class="poster">
              <img class="copertina" v-if="movie.poster_path === null" src="https://i.pinimg.com/564x/01/e1/35/01e135a5bcabe81ce279076de8dfbfd9.jpg" alt="">
              <img class="copertina" v-else :src="`https://image.tmdb.org/t/p/w342${movie.poster_path}`" alt="">
        
              <div class="container-info">
                <div class="info">{{movie.title}}</div>
                <div class="info">{{movie.original_title}}</div>
                <div class="bandiera-lingua info" v-if="movie.original_language === 'en'"><img :src="require('@/assets/bandiera-inglese.jpg')" alt="bandiera inglese"></div>
                <div class="bandiera-lingua info" v-else-if="movie.original_language === 'it'"><img :src="require('@/assets/bandiera-italiana.jpg')" alt="bandiera italiana"></div>
                <div class="bandiera-lingua info" v-else><img :src="require('@/assets/bandiera-lgbt.jpg')" alt="bandiera lgbt"></div>

                <div class="info">
                  <span><i  v-for="i in createvote(movie)" :key="i" class="fas fa-star"></i></span>
                  <span><i v-for="x in starsvuote" :key="x" class="far fa-star"></i></span>
                </div> 

                <div v-if="movie.overview" class="info">Description:{{movie.overview}}</div>

              </div>
            </div>
        </li>

        <li v-for="serie in  detailstv" :key="serie.id">
          <div class="poster">
            <img  class="copertina" v-if="serie.poster_path === null" src="https://i.pinimg.com/564x/01/e1/35/01e135a5bcabe81ce279076de8dfbfd9.jpg" alt="">
            <img class="copertina" v-else :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
        
            <div class="container-info">
              <div class="info">{{serie.name}}</div>
              <div class="info">{{serie.original_name}}</div>
              <div class="bandiera-lingua info" v-if="serie.original_language === 'en'"><img :src="require('@/assets/bandiera-inglese.jpg')" alt="bandiera inglese"></div>
              <div class="bandiera-lingua info" v-else-if="serie.original_language === 'it'"><img :src="require('@/assets/bandiera-italiana.jpg')" alt="bandiera italiana"></div>
              <div class="bandiera-lingua info" v-else><img :src="require('@/assets/bandiera-lgbt.jpg')" alt="bandiera lgbt"></div>

              <div class="info">
                <span><i v-for="(abc, i) in createvote(serie)" :key="i" class="fas fa-star"></i></span>
                <span><i v-for="(def, x) in starsvuote" :key="x" class="far fa-star"></i></span>
              </div> 
              <div v-if="serie.overview" class="info">Description:{{serie.overview}}</div>

          </div>
        </div>
      </li>
    </ul>
    </div>
  </div>
</template>

<script>


export default {
  name: 'Mymain',
  data() {
    return {
      numero: 0
  }},
  props:{
    details: Array,
    detailstv: Array
  },
  created() {

},
methods: {
  createvote(item){
  this.numero = Math.floor(item.vote_average / 2)
  return this.numero
  },
},
computed:{
  starsvuote(){
    let mancanti = 5 - this.numero
    return mancanti
  },
}
}



</script>

<style scoped lang="scss">
#gray-bg {
  background-color: gray;
  padding: 40px 0;
  min-height: 100vh;
  #container-posters{
    width: 80%;
    margin: 0px auto;
  }
}
li {
  list-style: none;
  padding: 10px;
}
.poster{
  border: 2px solid white;
  height: 513px;
  width: 342px;
  background-color: black;
  &:hover .copertina{
    display: none;
  }
  .container-info {
    display: flex;
    flex-direction: column;
    display: none;
    color: white;
    height: 100%;
    width: 100%;
    padding: 5px;
    overflow: scroll ;
    overflow-x:hidden;
    .info{
      margin:10px
    }
  }
  
    &:hover .container-info{
      display: flex;
    }
  }
.copertina {
  height: 100%;
  max-width: 100%;
}

ul{
  display: flex;
  flex-wrap: wrap;
}
.bandiera-lingua {
height: 20px;
  img {
    max-height: 100%;
    width: auto;
  }
}
</style>
