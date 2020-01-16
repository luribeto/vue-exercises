<template>
    <div class="col-xs-12 col-sm-6">
      <div v-if="server">
          <p>Server ID: {{ server.id }}</p>
          <p>Server Status: {{ server.status }}</p>
          <button @click="changeStatus">Normalize Server</button>
      </div>
      <div v-else>
        No server selected. Please click a server to get status details
      </div>
    </div>
</template>

<script>
import { serverBus } from '../../main';

export default {
  data: function() {
    return {
      server: null,
    }
  },
  methods: {
    changeStatus() {
      this.server.status = 'Normal';
    }
  },
  created() {
    serverBus.$on('serverSelected', (selectedServer) => {
      this.server = selectedServer;
    })
  }
}
</script>

<style>
</style>
