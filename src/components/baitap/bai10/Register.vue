<template>
    <div>
      <h2>Đăng nhập tài khoản</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="form.email" required />
        </div>
        <div>
          <label for="password">Mật khẩu:</label>
          <input type="password" id="password" v-model="form.password" required />
        </div>
        <button type="submit">Đăng nhập</button>
      </form>
      <p v-if="message" :class="{ 'success': isSuccess, 'error': !isSuccess }">{{ message }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          email: '',
          password: ''
        },
        message: '',
        isSuccess: false
      };
    },
    methods: {
      validateForm() {
        return this.form.email.trim() !== '' && this.form.password.trim() !== '';
      },
  
      submitForm() {
        if (!this.validateForm()) {
          this.message = 'Email và Mật khẩu không được để trống.';
          this.isSuccess = false;
          return;
        }
  
        const users = JSON.parse(localStorage.getItem('users')) || [];
        
        const user = users.find(user => user.email === this.form.email && user.password === this.form.password);
  
        if (user) {
          this.message = 'Đăng nhập thành công';
          this.isSuccess = true;
        } else {
          this.message = 'Đăng nhập thất bại';
          this.isSuccess = false;
        }
      }
    }
  };
  </script>
  
  <style scoped>
  .success {
    color: green;
  }
  .error {
    color: red;
  }
  </style>