<template>
  <header>
    <!-- logo -->
    <div class="logo">
        boolfix
    </div>

    <!-- search bar -->
    <div class="search">
        <input type="text" v-model="searchText" @keyup.enter="$emit('userInput', searchText)">
        <button @click="$emit('userInput', searchText)">Search</button>
    </div>
  </header>
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
    header {
        background-color: black;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 2rem;
        height: 100px;

        .logo {
            color: red;
            font-size: 2rem;
            text-transform: uppercase;
        }
    }
</style>