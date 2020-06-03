<template>
  <div class="movieView container">
    <h3 class="my-4">나만의 무비 컬렉션</h3>
    <button v-if="movies.length === 0" @click="getMovieData" class="btn btn-primary">영화 가져오기</button>

    <MovieList :movies="movies"/>
  </div>
</template>

<script>
import axios from 'axios'
import MovieList from '@/components/MovieList.vue'

const MOVIE_API_URL = 'http://www.json-generator.com/api/json/get/ceNyuXZmwi?indent=2'


export default {
  name: 'MovieView',
  components: {
    MovieList
  },
  data () {
    return {
      movies: [],
    }
  },
  methods: {
    getMovieData(){
      axios.get(MOVIE_API_URL)
        .then(res => 
        this.movies = res.data
        // console.log('밍?', res.data[0].poster_url)
        )
        .catch(err => console.error(err))
    }
  }
}
</script>
