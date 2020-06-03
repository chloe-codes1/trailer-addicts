<template>
    <div class="mb-5">
        <input @keypress.enter="onInput" id="input" class="">
        <button @click="onInput" class="btn search-button">검색</button>       
    </div>
</template>

<script>
export default {
    name: 'VideoSearch',
    methods: {
        onInput(event) {
            const searchText = document.getElementById("input").value
            this.$emit('input-change', searchText)
            event.target.value = ''
        }
    }
}
</script>

<style>
.search-button{
  background-color: #3fb883;
  color: white;
  font-size: 0.8rem;
  padding: 5px, 8px;
  margin-left: 5px;
}
</style>