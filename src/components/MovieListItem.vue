<template>
  <div class="movieListItem col-md-12 col-lg-4 col-xl-3">
    <div class="card" style="width: 100%">
      <img class="card-img-top" :src="posterURL" alt="movie-poster-image">
      <div class="card-body">
        <h5 class="card-title">{{movie.title}}</h5>
        <MovieListItemModal :movie="movie"/>
      </div>
    </div>
  </div>
</template>

<script>
import MovieListItemModal from './MovieListItemModal.vue'
export default {
  name: 'MovieListItem',
  components: {
    MovieListItemModal
  },
  props: {
    movie: Object,
  },
  computed: {
    posterURL() {
      return this.movie.poster_url
    }
  }

}
</script>

<style>

</style>