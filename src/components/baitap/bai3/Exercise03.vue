<template>
  <div>
    <h3>Ngày sinh:</h3>
    <input type="date" v-model="birthDate" />
    <p>Ngày sinh: {{ formattedBirthDate }}</p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue';
const birthDate = ref('');

const formattedBirthDate = computed(() => {
  if (!birthDate.value) return '';
  const date = new Date(birthDate.value);
  const day = String(date.getDate()).padStart(2, '0');
  const month = String(date.getMonth() + 1).padStart(2, '0');
  const year = date.getFullYear();
  return `${day}/${month}/${year}`;
});
</script>

<style scoped>
input { 
  margin-bottom: 10px;
  padding: 5px;
  width: 150px;
}

p {
  font-weight: bold;
}
</style>
