<template>
  <div>
    <h3>Màu sắc</h3>
    <input type="color" v-model="color" />
    <div 
      :style="{ backgroundColor: color, width: '100px', height: '50px', border: '1px solid #000', marginTop: '10px' }">
    </div>
    <p>Mã màu: {{ color }}</p>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const color = ref('#000000');
</script>

<style scoped>
p {
  font-weight: bold;
}

input {
  margin-bottom: 10px;
}

div {
  display: inline-block;
}
</style>
