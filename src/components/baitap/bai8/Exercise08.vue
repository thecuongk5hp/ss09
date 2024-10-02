<template>
    <div>
      <h2>Đăng ký tài khoản</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name">Tên:</label>
          <input type="text" id="name" v-model="user.name" required />
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="user.email" required />
        </div>
        <div>
          <label for="password">Mật khẩu:</label>
          <input type="password" id="password" v-model="user.password" required />
        </div>
        <div>
          <label for="confirmPassword">Nhập lại mật khẩu:</label>
          <input type="password" id="confirmPassword" v-model="confirmPassword" required />
        </div>
        <button type="submit">Đăng ký</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        user: {
          name: '',
          email: '',
          password: ''
        },
        confirmPassword: ''
      };
    },
    methods: {
      submitForm() {
        if (this.user.password !== this.confirmPassword) {
          alert('Mật khẩu và Nhập lại mật khẩu không khớp!');
          return;
        }
        
        console.log(this.user);
  
      }
    }
  };
  </script>
  
  <style scoped>
  </style>