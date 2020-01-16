<template>
  <div class="container">
    <div class="row">
      <app-quote>
        <h2>My quote</h2>
      </app-quote>
    </div>
  </div>
</template>

<script>
  import Quote from './components/Quote.vue';

  export default {
    components: {
      appQuote: Quote,
    }
  }
</script>

<style>

</style>
