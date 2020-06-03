<template>
  <div class="videoItemDetail">
    <li @click="onVideoSelect" class="video-item list-group-item">
      <div class="media-body py-3">
        {{ video.snippet.title }}
      </div>
      <div class="embed-responsive embed-responsive-16by9">
        <iframe
        type="text/html" class="video-iframe embed-responsive-item"
        :src="videoUrl"
        allowfullscreen
        ></iframe>       
      </div>
      
  </li>
  </div>
</template>

<script>
export default {
    name: 'VideoItemDetail',
    props: {
        video: Object
    },
    methods: {
        onVideoSelect() {
            this.$emit('video-select', this.video)
        }
    },
    computed: {
        videoUrl() {
            return `https://youtube.com/embed/${this.video.id.videoId}`
        },
        
    }
}
</script>

<style>

</style>