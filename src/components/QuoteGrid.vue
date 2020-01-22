<template>
    <div class="row">
      <app-quote v-for="(quote, idx) in quotes" :key="idx">
        {{ quote }}
      </app-quote>
    </div>
</template>

<script>
  import Quote from './Quote.vue';

  export default {
    props: ['quotes'],
    components: {
      "app-quote": Quote,
    }
  }
</script>

<style>
</style>
