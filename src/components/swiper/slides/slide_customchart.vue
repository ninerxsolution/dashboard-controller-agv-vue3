<template>

  <div class="container-fluid content pt-3">
    <div class="row">
      {{ userId }} {{ jsonData }}
      <div v-for="user in users" v-bind:key="user.id">
        {{ user.address.suite }}
      </div>
    </div>
</div>
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




