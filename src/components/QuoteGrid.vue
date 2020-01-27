<template>
    <div class="row">
      <app-quote v-for="(quote, idx) in quotes" :key="idx" @click.native="deleteQuote(idx, $event)">
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
    },
    methods: {
      deleteQuote(idx, ev, par1, par2) {
        this.$emit('quoteDeleted', idx);
      }
    }
  }
</script>

<style>
</style>
