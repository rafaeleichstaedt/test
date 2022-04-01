
<template>
  <v-app id="inspire">
    <v-main>
      <Dashboard />
    </v-main>
  </v-app>
</template>

<script>
  import Dashboard from './views/Dashboard.vue'
  export default {
    components: {
      Dashboard,
    },
  }
</script>