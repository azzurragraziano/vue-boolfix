<template>
  <section class="cards container">
    <li>
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
            vote: {{item.vote_average}}
          </li>
        </ul>
    </li>
  </section>
</template>

<script>

export default {
    name: "CardsComponent",
    props: {
        item: Object
    },
    data() {
      return {

      }
    }
}
</script>

<style>

</style>