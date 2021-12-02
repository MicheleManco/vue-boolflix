<template>
  <div id="app">
    <Myheader @searchtv="savearraytv" @search="savearray"/>
    <Mymain :details="arraymovies" :detailstv="arrayseries"/>
  </div>
</template>

<script>
import Mymain from './components/Mymain.vue'
import Myheader from './components/Myheader.vue'

export default {
  name: 'App',
  components: {
    Mymain,
    Myheader
  },
  data(){
    return {
      arraymovies:[],
      arrayseries:[]
    }
  },
  methods:{
    savearray(res){
      this.arraymovies = res
    },
     savearraytv(res){
      this.arrayseries = res
    }
  }
}
</script>

<style lang="scss">

</style>
