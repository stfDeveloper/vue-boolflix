<template>
  <div id="app">
    <Main/>
  </div>
</template>

<script>
import Main from './components/Main.vue'



export default {
  name: 'App',
  data(){
    return {
      arrayMovies:[]
    }
  },
  components: {
    Main
  },
  methods:{
   
  },
}

</script>

<style lang="scss">
@import"./assets/style/global.scss";

</style>
