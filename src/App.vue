<template>
  <div class="container">
    <div class="row">
      <div class="col-xs-12" style="padding: 20px 0">
        <button @click="selectedComponent = 'app-quote'">Quote</button>
        <button @click="selectedComponent = 'app-author'">Author</button>
        <button @click="selectedComponent = 'app-new'">New</button>
        <hr>
        <p>{{ selectedComponent }}</p>
        <component :is="selectedComponent">
          <p>Default passed content</p>
        </component>
        <!-- <app-quote>
          <h2 slot="title">{{ quoteTitle }}</h2>
          <p>middle</p>
          <p>some external text</p>
        </app-quote> -->
      </div>
    </div>
  </div>
</template>

<script>
  import quote from './components/quote.vue';
  import Author from './components/Author.vue';
  import NewQuote from './components/NewQuote.vue';

  export default {
    data: function() {
      return {
        quoteTitle: 'The Quote from parent',
        selectedComponent: 'app-quote'
      }
    },
    components: {
      "app-quote": quote,
      "app-author": Author,
      "app-new": NewQuote,
    }
  }
</script>

<style>
</style>
