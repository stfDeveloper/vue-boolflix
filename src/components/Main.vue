<template>
  <div class="p-1 text-center">
    <Header @showFilter="showResults" />
    <div id="picker_section">
      <Lista :movies="arrayMovies" :tvSeries="arraySeries" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Lista from "../sections/Lista.vue";
import Header from "./Header.vue";

export default {
  name: "Main",
  components: {
    Lista,
    Header,
  },
  data() {
    return {
      inputCerca: "",
      arrayMovies: [],
      arraySeries: [],
    };
  },
  methods: {
    showResults: function (pick) {
      this.inputCerca = pick;
      this.prendiData();
      this.prendiDataSeries();
    },
    prendiData: function () {
      axios
        .get("https://api.themoviedb.org/3/search/movie?", {
          params: {
            api_key: "6cc9ce725507612c5c8a67cdfd9800bc",
            query: this.inputCerca,
          },
        })
        .then((response) => {
          this.arrayMovies = response.data.results;
        })
        .catch(function (error) {
          console.log(error);
        });
    },
    prendiDataSeries: function () {
      axios
        .get("https://api.themoviedb.org/3/search/tv", {
          params: {
            api_key: "6cc9ce725507612c5c8a67cdfd9800bc",
            query: this.inputCerca,
          },
        })
        .then((response_TV) => {
          this.arraySeries = response_TV.data.results;
          console.log("arraySeries");
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss" scoped>
#picker_section {
  background-color: rgba(255, 0, 0, 0.603);
  min-width: 100%;
  height: calc(100vh - 100px);
  overflow-y: scroll;

  border-radius: 40px;
}
::-webkit-scrollbar {
  display: none;
}
</style>
