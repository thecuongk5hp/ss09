<template>
    <div>
      <h2>Kiểm tra tiến độ hoàn thành công việc:</h2>
      <input type="range" v-model="progress" min="0" max="100" />
      <p>Tiến độ hiện tại: <strong>{{ progress }}%</strong></p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        progress: 0 
      };
    }
  };
  </script>
  
  <style scoped>

  </style>