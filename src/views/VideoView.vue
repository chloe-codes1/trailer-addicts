<template>
  <div class="videoView container m-auto">
      <div v-if="videos.length === 0" class="centered"></div>
      <h3 class="mt-5 mb-4">영화 예고편 검색</h3>
      <VideoSearch @input-change="onInputChange" />
      <div>
          <VideoItem :videos="videos"/> 
      </div>
      <button v-if="videos.length > 0" @click="scrollToTop" class="button-bottom btn">Top</button>
  </div>
</template>

<script>
const API_KEY = process.env.VUE_APP_YOUTUBE_API_KEY
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
            axios.get(API_URL, {
                params: {
                    key: API_KEY,
                    part: 'snippet',
                    type: 'video',
                    q: this.inputValue
                }
            })
            .then(res => {
                res.data.items.forEach(item => {
                    const parser = new DOMParser()
                    const doc = parser.parseFromString(item.snippet.title, 'text/html')
                    item.snippet.title = doc.body.innerText
                })
                this.videos = res.data.items
            })
            .catch(err => console.error(err))
        },
          scrollToTop: function(){
                scroll(0,0) // 맨 위로 올리기 = > window는 전역객체라서 생략함
            },
    }
}
</script>

<style>
    .centered {
    height:100px;
    }


    .videoView {
        margin : 20px;
    }
    .button-bottom {
    position: fixed;
    right: 4vw;
    bottom: 2vh;
    padding: 4px 8px;
    background-color: #3fb883;
    color: white;
    font-weight: bold;
}
</style>
