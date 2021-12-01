<template>
  <div>
    <ul>
      <li v-for="movie,i in  details" :key="i">
        <div>{{movie.title}}</div>
        <div>{{movie.original_title}}</div>
        <div>{{movie.original_language}}</div>
        <div>{{movie.vote_average}}</div>
      </li>
    </ul>
  </div>
</template>

<script>


export default {
  name: 'Mymain',
  props:{
    details:Array
  },
  data() {
  return {
    
  }
},
created() {
},
methods: {
  
}
}



</script>

<style scoped lang="scss">

</style>
