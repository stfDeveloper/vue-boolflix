<template>
<div>
    <input id="input" class="text-center" type="text" placeholder="Cerca film o serie TV" v-model="input" @keyup="$emit('find',input)">
</div>
  
</template>

<script>
export default {
    name: 'Search',
    data(){
        return{
            input:""

        }
    }

}
</script>

<style lang="scss">
#input {
  border-radius: 20px;
  border: 1px solid rgba(0, 0, 0, 0.247);
  margin-top: 20px;
}
#button {
  border-radius: 20px;
  border: 1px solid rgba(0, 0, 0, 0.247);
  margin-left: 10px;
  background-color: rgba(255, 0, 0, 0.603);
  color: white;
}

</style>