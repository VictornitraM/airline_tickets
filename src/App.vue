<template>
  <div id="app">
    <AirlineTicket></AirlineTicket>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import AirlineTicket from './components/airline_ticket.vue'


export default Vue.extend({
  name: 'App',
  components: {
    AirlineTicket
  }
});
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
