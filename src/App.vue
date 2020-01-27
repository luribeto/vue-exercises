<template>
    <div class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      <app-quote-grid :quotes="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert atert-info">Info: Click on a quote to delete it!!</div>
        </div>
      </div>
    </div>
</template>

<script>
  import Header from './components/Header.vue';
  import NewQuote from './components/NewQuote.vue';
  import QuoteGrid from './components/QuoteGrid.vue';

  export default {
    data: () => ({
      quotes: [],
      maxQuotes: 10,
    }),
    methods: {
      newQuote(newQuote) {
        if (this.quotes.length >= this.maxQuotes) return alert('Maximum quotes limit reached!!! Please delete quotes to add new ones');
        this.quotes.push(newQuote);
      },
      deleteQuote(idx) {
        this.quotes.splice(idx, 1);
      }
    },
    components: {
      "app-header": Header,
      "app-quote-grid": QuoteGrid,
      "app-new-quote": NewQuote,
    }
  }
</script>

<style>
</style>
