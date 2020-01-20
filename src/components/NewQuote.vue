<template>
  <div>
    <h3>New Quote</h3>
    <button @click="counter++">Increase!</button>
    <p>{{ counter }}</p>
  </div>
</template>

<script>
  export default {
    data: () => ({
      counter: 0,
    }),
    destroyed: function() {
      console.log('destroyed')
    }
  }
</script>

<style>
</style>