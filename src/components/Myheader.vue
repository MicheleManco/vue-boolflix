<template>
  <div>
    <input type="text" placeholder="cerca" v-model="query">
    <button>cerca</button>
  </div>
</template>

<script>
export default {
  name: 'Myheader',
  data() {
  return {
    query: ""
  }
},
created() {
  console.log(this.query)
},
methods:{


}

}

</script>

<style scoped lang="scss">

</style>