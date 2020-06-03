<template>
    <div>
        <input @keypress.enter="onInput" id="input">
        <button @click="onInput">검색</button>       
    </div>
</template>

<script>
export default {
    name: 'VideoSearch',
    methods: {
        onInput() {
            const searchText = document.getElementById("input").value
            this.$emit('input-change', searchText)
        }
    }
}
</script>

<style>

</style>