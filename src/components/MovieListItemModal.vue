<template>
  <div class="movieListItemModal">
    <button class="btn modal-trigger-button" data-toggle="modal" :data-target="`#movieDetail-${movie.id}`">영화 정보 상세보기</button>
   
    <!-- Modal -->
    <div class="modal fade " :id="'movieDetail-'+movie.id" tabindex="-1" role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
      <div class="modal-dialog" role="document">
        <div class="modal-content">
          <div class="modal-header">
            <h5 class="modal-title" id="exampleModalLabel">{{movie.title}}</h5>
            <button type="button" class="close" data-dismiss="modal" aria-label="Close">
              <span aria-hidden="true">&times;</span>
            </button>
          </div>
          <div class="modal-body">
            <img class="card-img-top" :src="posterURL" alt="movie-poster-image">
            <p class="rating-area">{{movie.user_rating}} 점</p>
            <div>{{movie.overview}}</div>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
          </div>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "MovieListItemModal",
  props: {
    movie: Object
  },
  computed: {
    posterURL() {
      return this.movie.poster_url
    }
  }
}
</script>

<style>
.modal-trigger-button{
  background-color:  #3fb883;
  color:white;
}

.rating-area{
  background-color: #3fb883;
  font-weight: bold;
}
</style>