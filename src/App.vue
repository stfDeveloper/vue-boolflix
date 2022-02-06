<template>
  <div id="app">
    <Header/>
    <Main/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'



export default {
  name: 'App',
  data(){
    return {
      arrayMovies:[]
    }
  },
  components: {
    Main,
    Header
  },
  methods:{
   
  },
}

</script>

<style lang="scss">
@import"./assets/style/global.scss";

</style>
