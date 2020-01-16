<template>
  <li class="list-group-item" @click="getDetails">
      Server #{{ server.id }}
  </li>
</template>

<script>
import { serverBus } from '../../main';

export default {
  props: ['server'],
  methods: {
    getDetails() {
      serverBus.$emit('serverSelected', this.server)
    }
  }
}
</script>

<style>
</style>


