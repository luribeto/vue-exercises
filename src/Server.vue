<template>
  <li class="list-group-item">
      Server #{{ serverUniqueId }}
  </li>
</template>

<script>
export default {
  data: function() {
    debugger;
    return {
      serverUniqueId: `${this.server} - Leos`
    }
  }
}
</script>

<style>
</style>


