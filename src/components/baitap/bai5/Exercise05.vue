<template>
  <div>
    <h3>Trước khi người dùng lựa chọn:</h3>
    <div>Giới tính:</div>
    <label>
      <input type="radio" value="Nam" v-model="gender" /> Nam
    </label>
    <label>
      <input type="radio" value="Nữ" v-model="gender" /> Nữ
    </label>
    <label>
      <input type="radio" value="Khác" v-model="gender" /> Khác
    </label>

    <h3>Sau khi người dùng lựa chọn:</h3>
    <div>Giới tính: {{ gender }}</div>
    <label>
      <input type="radio" value="Nam" v-model="gender" /> Nam
    </label>
    <label>
      <input type="radio" value="Nữ" v-model="gender" /> Nữ
    </label>
    <label>
      <input type="radio" value="Khác" v-model="gender" /> Khác
    </label>
  </div>
</template>

<script setup>
  const Exercise05 = {
    data() {
      return {
        gender: ''
      };
    }
  };
</script>

