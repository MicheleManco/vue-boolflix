<template>
  <div>
    <ul>
      <li v-for="movie,i in  details" :key="i">
        <div>{{movie.title}}</div>
        <div>{{movie.original_title}}</div>
        <div class="bandiera-lingua" v-if="movie.original_language === 'en'"><img :src="require('@/assets/bandiera-inglese.jpg')" alt="bandiera inglese"></div>
        <div class="bandiera-lingua" v-else-if="movie.original_language === 'it'"><img :src="require('@/assets/bandiera-italiana.jpg')" alt="bandiera italiana"></div>
        <div class="bandiera-lingua" v-else><img :src="require('@/assets/bandiera-lgbt.jpg')" alt="bandiera lgbt"></div>
        <div>{{movie.vote_average}}</div>
      </li>
      <li v-for="serie,i in  detailstv" :key="i">
        <div>{{serie.name}}</div>
        <div>{{serie.original_name}}</div>
        <div class="bandiera-lingua" v-if="serie.original_language === 'en'"><img :src="require('@/assets/bandiera-inglese.jpg')" alt="bandiera inglese"></div>
        <div class="bandiera-lingua" v-else-if="serie.original_language === 'it'"><img :src="require('@/assets/bandiera-italiana.jpg')" alt="bandiera italiana"></div>
        <div class="bandiera-lingua" v-else><img :src="require('@/assets/bandiera-lgbt.jpg')" alt="bandiera lgbt"></div>
        <div>{{serie.vote_average}}</div>
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'Mymain',
  props:{
    details:Array,
    detailstv: Array
  },
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
