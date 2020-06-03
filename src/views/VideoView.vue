<template>
  <div class="videoView">
      <h3>영화 예고편 검색</h3>
      <VideoSearch @input-change="onInputChange" />
      <div>
          <VideoItem :videos="videos"/> 
      </div>
  </div>
</template>

<script>
const API_KEY = 'AIzaSyBmcUHV6y_ocELwi58_FhP0MeZTpRSl7CI'
const API_URL = 'https://www.googleapis.com/youtube/v3/search'

import axios from 'axios'
import VideoSearch from '@/components/VideoSearch'
import VideoItem from '@/components/VideoItem'

export default {
    name: 'VideoView',
    components: {
        VideoSearch,
        VideoItem,
    },
    data() {
        return {
          inputValue: '',
          videos: [],
        }
    },
    methods: {
        onInputChange(inputText) {
            this.inputValue = inputText + 'trailer'
            console.log(this.inputValue)
            axios.get(API_URL, {
                params: {
                    key: API_KEY,
                    part: 'snippet',
                    type: 'video',
                    q: this.inputValue
                }
            })
            .then(res => this.videos = res.data.items)
            .catch(err => console.error(err))
        
        }
    }
}
</script>

<style>
    .videoView {
        margin : 20px;
    }
</style>
