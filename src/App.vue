<template>
  <div id="app">
    <Dashboard></Dashboard>
    อันนี้แบบว่าทดสอบนะว่ามันจะเป็นยังไง
    อันนี้ทดสอบ Pulling fetch นะะะะ โหล้ๆ
    ทดสอบอีกรอบนะ อันนี้ commit มาจาก branch ชื่ออื่น ๆ
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
