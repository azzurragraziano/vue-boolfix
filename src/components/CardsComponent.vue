<template>
  <li class="card">
    <ul>
      <!-- title -->
      <li>
        Title: {{item.title}}
      </li>
      <!-- original title -->
      <li>
        Original Title: {{item.original_title}}
      </li>

      <!-- language -->
      <li>
        Language: {{item.original_language}}
      </li>

      <!-- vote -->
      <li>
        Vote: {{item.vote_average}}
      </li>
    </ul>
  </li>
</template>

<script>

export default {
  name: "CardsComponent",
  props: {
      item: Object
  }
}
</script>

<style lang="scss" scoped>
  .card {
    background-color: gray;
    width: calc((100% / 3) - 5px);
    padding: 5px;
    margin: 2.5px;
  }
</style>