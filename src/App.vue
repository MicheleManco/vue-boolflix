<template>
  <div id="app">
    <Myheader @search="savearray"/>
    <Mymain :details="arraymovies"/>
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
      arraymovies:[]
    }
  },
  methods:{
    savearray(res){
      this.arraymovies = res
    }
  }
}
</script>

<style lang="scss">

</style>
