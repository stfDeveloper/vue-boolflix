<template>
  <div class="p-1 text-center">
    <input
      type="text"
      id="input"
      v-model="inputCerca"
      @keyup.enter="prendiData"
    />
    <button id="button" @click="prendiData">Cerca</button>
    <div
      id="picker_section"
    >
      <ul class="d-flex justify-content-center p-2 flex-wrap">
        <li id="card" class="flex-column" v-for="(element, index) in arrayMovies" :key="index">
          <p>Titolo:{{ element.original_title}} </p>
          <p>Lingue:{{ element.original_language }} </p>
          <p>Voto:{{ element.vote_average }} </p>

        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Main",
  components: {},
  data() {
    return {
      inputCerca: "",
      arrayMovies: [],
    };
  },
  methods: {
    prendiData: function () {
      axios
        .get("https://api.themoviedb.org/3/search/movie", {
          params: {
            api_key: "6cc9ce725507612c5c8a67cdfd9800bc",
            query: this.inputCerca,
          },
        })
        .then((response) => {
          this.arrayMovies = response.data.results;
          console.log("arrayMovies");
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss" scoped>
#input {
  border-radius: 20px;
  border: 1px solid rgba(0, 0, 0, 0.247);
  margin-bottom: 10px;
}
#button {
  border-radius: 20px;
  border: 1px solid rgba(0, 0, 0, 0.247);
  margin-left: 10px;
  background-color: rgba(255, 0, 0, 0.603);
  color: white;
}
#picker_section {
  background-color: rgba(255, 0, 0, 0.603);
  min-width: 100%;
  height: calc(100vh - 250px);
  overflow-y: scroll;

  border-radius: 40px;
}
::-webkit-scrollbar {
  display: none;
}
.content {
  width: 50px;
  height: 70px;
  background-color: blue;
}
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
