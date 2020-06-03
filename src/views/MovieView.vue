<template>
  <div class="movieView container">
    <div v-if="movies.length === 0" class="centered"></div>
    <h3 class="mt-5 mb-4">나만의 영화 저장소</h3>
    <button v-if="movies.length === 0" @click="getMovieData" class="btn get-movies-button">영화 가져오기</button>

    <MovieList :movies="movies"/>
    <button v-if="movies.length > 0" @click="scrollToTop" class="button-bottom-clear btn">Top</button>
  </div>
</template>

<script>
import axios from 'axios'
import MovieList from '@/components/MovieList.vue'

const MOVIE_API_URL = 'https://www.json-generator.com/api/json/get/ceNyuXZmwi?indent=2'


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
        .then(res => this.movies = res.data)
        .catch(err => console.error(err))
    },
    scrollToTop: function(){
                scroll(0,0) 
            },
  }
}
</script>

<style scoped>
.centered {
  height:120px;
}

.button-bottom-clear {
    position: fixed;
    right: 4vw;
    bottom: 2vh;
    border: 1px solid #3fb883;
    padding: 4px 8px;
    color: #3fb883;
    font-weight: bold;
}
  .get-movies-button{
    background-color: #3fb883;
    color: white;
    margin-top:20px;
  }

  
</style>