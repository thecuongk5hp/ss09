<template>
  <div>
    <h3>Email</h3>
    <input type="email" v-model="email" placeholder="Nhập email của bạn" />
    <p>Giá trị: {{ email }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const email = ref('');
</script>

<style scoped>
input {
  margin-bottom: 10px;
  padding: 5px;
  width: 250px;
}

p {
  font-weight: bold;
}
</style>
