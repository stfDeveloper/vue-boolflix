<template>
<div class="header_wrap d-flex justify-content-around">
    <div class="" id="header">
        <img src="../assets/style/logo.png" alt="">
    </div>
     <Search @find="filter"/>
</div>
</template>


<script>
import Search from "../sections/Search.vue"


export default {
    name: "Header",
    components:{
        Search,

    },
    methods:{
         filter: function(inputFilter){
          this.$emit('showFilter',inputFilter)
      },
    }
} 
</script>

<style lang="scss" scoped>
#header{
    width: 60%;
    max-height: 100px;
    img{
        width: 20%;
    }
}
</style>