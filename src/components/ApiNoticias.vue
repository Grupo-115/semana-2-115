<template>
    <div>
        <div class="container">
        <div class="row mt-md-5 mt-sm-5 mt-xs-5">
        <div class="col-lg-6 col-xs-12"  v-for="(movie, index) of movies" :key="index">

        <hr>
        <div class="p-2">
            <h4>{{movie.title}}</h4>
        </div>

        <div class="d-flex justify-content-center align-items-center">
            <div class="">
            <img class = "mw-100" :src="movie.urlToImage" alt="imagen de la noticia">
            <p>{{movie.description}}</p>
        </div>

        <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
            <a :href="movie.url" class="btn btn-outline-info">Info</a>
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
    axios.get("http://newsapi.org/v2/top-headlines?country=co&apiKey=5355856527154b91adb06c794974862e")
      .then(response => {
        (this.movies = response.data.articles.slice(0, 4));
      });
  },
}
</script>