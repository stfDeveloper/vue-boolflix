<template>
<div>
    <div>
        <h1 v-if="movies.length>0">Film</h1>
        <ul class="d-flex justify-content-center p-2 flex-wrap">
            <li id="card" class="flex-column" v-for="(element, index) in movies" :key="'movies' + index">
                <p>Titolo:{{ element.original_title}} </p>
                    <p> Lingua:
                        <img class="w-25" v-if="element.original_language == 'it'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/2560px-Flag_of_Italy.svg.png" alt="">
                        <img class="w-25" v-else-if="element.original_language == 'en'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Flag_of_the_United_Kingdom.svg/640px-Flag_of_the_United_Kingdom.svg.png" alt="">
                        <img class="w-25" v-else-if="element.original_language == 'es'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Flag_of_Spain.svg/1024px-Flag_of_Spain.svg.png" alt="">
                    </p>
                <p>Voto:{{ element.vote_average }} </p>
                </li>
        </ul>
    </div>

    <div>
        <h1 v-if="tvSeries.length>0">TV Series</h1>
        <ul class="d-flex justify-content-center p-2 flex-wrap">
            <li id="card" class="flex-column" v-for="(element_series, index) in tvSeries" :key="'tvSeries' + index">
                <p>Titolo:{{ element_series.original_name}} </p>
                    <p> Lingua:
                        <img class="w-25" v-if="element_series.original_language == 'it'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/0/03/Flag_of_Italy.svg/2560px-Flag_of_Italy.svg.png" alt="">
                        <img class="w-25" v-else-if="element_series.original_language == 'en'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ae/Flag_of_the_United_Kingdom.svg/640px-Flag_of_the_United_Kingdom.svg.png" alt="">
                        <img class="w-25" v-else-if="element_series.original_language == 'es'" src="https://upload.wikimedia.org/wikipedia/commons/thumb/9/9a/Flag_of_Spain.svg/1024px-Flag_of_Spain.svg.png" alt="">
                    </p>
                <p>Voto:{{ element_series.vote_average }} </p>
                </li>
        </ul>
    </div>
</div>

  
</template>

<script>
export default {
    name: 'Lista',
    props:{
        movies: Array,
        tvSeries: Array
    }

}
</script>

<style lang="scss" scoped>
#card{
    padding: 20px;
    width: 150px;
    height: 250px;
    margin: 20px;
    background-color: white;
    list-style: none;
    font-size: 12px;
}

</style>