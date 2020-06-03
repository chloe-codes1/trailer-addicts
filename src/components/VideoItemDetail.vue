<template>
  <div class="videoItemDetail">
    <li @click="onVideoSelect" class="video-item list-group-item">
      <div class="media-body">
        {{ video.snippet.title }}
      </div>
      <div>
        <iframe
        :src="videoUrl"
        width="800px"
        height="400px"
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