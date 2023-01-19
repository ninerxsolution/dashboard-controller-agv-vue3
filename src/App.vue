<template>
  <div id="app">
    <Dashboard></Dashboard>
  </div>
</template>

<script>
import Dashboard from './components/layouts/dashboard_layout.vue';
export default {
  name: 'App',
  components: {
    Dashboard
  },
}
</script>

<style lang="scss">
@import '@/assets/css/style.css';
@import '@/assets/vendors/mdi/css/materialdesignicons.min.css';
</style>
