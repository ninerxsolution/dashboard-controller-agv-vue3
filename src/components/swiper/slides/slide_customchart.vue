<template>
    <div>
      <p>{{ message }}</p>
      <p>Last update: {{ time }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        message: 'Hello, Vue!',
        time: '',
      };
    },
    mounted() {
      setInterval(() => {
        this.message = 'The message was updated.';
        this.time = new Date().toLocaleString();
      }, 1000);
    },
  };
  </script>
  
  
  
  
  