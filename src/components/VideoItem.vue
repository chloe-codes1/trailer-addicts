<template>
    <div>
        <VideoItemDetail 
            @video-select="onVideoSelect"
            :video="video"
            v-for="video in videos"
            :key="video.etag"/>
    </div>
</template>

<script>
import VideoItemDetail from './VideoItemDetail.vue'

export default {
    name: 'VideoItem',
    components: {
        VideoItemDetail
    },
    props: {
        videos: Array,
    },
    methods: {
        onVideoSelect() {
            this.$emit('video-select', this.video)
        }
    },
    
}
</script>


<style>

</style>