<template>
    <div>
        <div class="container">
        <div class="row mt-md-5 mt-sm-5 mt-xs-5">
        <div class="col-lg-6 col-xs-12"  v-for="(movie, index) of movies" :key="index">

        <div class="d-flex justify-content-center align-items-center">
            <div class="p-3">
            <img :src="movie.Poster" alt="movie poster">
        </div>

        <div class="p-2">
            <h2>{{ movie.Title}}</h2>
            <hr>
            <p></p>
        </div>

    <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
      <a :href="'https://www.imdb.com/title/' + movie.imdbID" class="btn btn-outline-info">Info</a>
    </div>

  </div>
  </div>
  </div>
    </div>
    </div>
</template>

<script>
import axios from "axios";
export default {
  name: "ApiNoticias",
  data() {
    return {
      movies: null,
    };
  },
  mounted() {
    axios.get("http://www.omdbapi.com/?s=harry+potter&type=movie&apikey=349c3dd5")
      .then(response => {
        (this.movies = response.data.Search.slice(0, 4));
      });
  },
}
</script>