<template>
  <div class="header-content">
    <div class="logo">
        boolfix
    </div>

    <div class="search">
        <input type="text" v-model="searchText" @keyup.enter="$emit('userInput', searchText)">
        <button @click="$emit('userInput', searchText)">Search</button>
    </div>
  </div>
</template>

<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            searchText: ''
        }
    }
}
</script>

<style lang="scss" scoped>
.header-content {
    background-color: black;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 2rem;

    .logo {
        color: red;
        font-size: 2rem;
        text-transform: uppercase;
    }
}
</style>