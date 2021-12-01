<template>
  <div id="app">
    <Myheader/>
    <Mymain/>
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
  }
}
</script>

<style lang="scss">

</style>
