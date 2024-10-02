<template>
    <div>
      <h2>Đăng ký tài khoản</h2>
      <form @submit.prevent="submitForm">
        <div>
          <label for="name">Tên sinh viên:</label>
          <input type="text" id="name" v-model="form.name" required />
          <span v-if="errors.name" class="error">{{ errors.name }}</span>
        </div>
        <div>
          <label for="email">Email:</label>
          <input type="email" id="email" v-model="form.email" required />
          <span v-if="errors.email" class="error">{{ errors.email }}</span>
        </div>
        <div>
          <label for="password">Mật khẩu:</label>
          <input type="password" id="password" v-model="form.password" required />
          <span v-if="errors.password" class="error">{{ errors.password }}</span>
        </div>
        <div>
          <label for="address">Địa chỉ:</label>
          <input type="text" id="address" v-model="form.address" />
        </div>
        <button type="submit">Đăng ký</button>
      </form>
      <p v-if="successMessage">{{ successMessage }}</p>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        form: {
          name: '',
          email: '',
          password: '',
          address: ''
        },
        errors: {
          name: null,
          email: null,
          password: null
        },
        successMessage: ''
      };
    },
    methods: {
      validateForm() {
        let valid = true;
  
        this.errors.name = null;
        this.errors.email = null;
        this.errors.password = null;
  
        if (!this.form.name) {
          this.errors.name = 'Tên sinh viên không được để trống.';
          valid = false;
        }
  
        if (!this.form.email) {
          this.errors.email = 'Email không được để trống.';
          valid = false;
        } else if (this.isEmailDuplicate(this.form.email)) {
          this.errors.email = 'Email đã tồn tại.';
          valid = false;
        }
  
        if (!this.form.password) {
          this.errors.password = 'Mật khẩu không được để trống.';
          valid = false;
        }
  
        return valid;
      },
  
      isEmailDuplicate(email) {
        const users = JSON.parse(localStorage.getItem('users')) || [];
        return users.some(user => user.email === email);
      },
  
      submitForm() {
        if (this.validateForm()) {
          const users = JSON.parse(localStorage.getItem('users')) || [];
          users.push({ ...this.form });
          localStorage.setItem('users', JSON.stringify(users));
  
          this.successMessage = 'Đăng ký tài khoản thành công';
  
          this.resetForm();
  
          this.$nextTick(() => {
            document.getElementById('name').focus();
          });
        }
      },
  
      resetForm() {
        this.form.name = '';
        this.form.email = '';
        this.form.password = '';
        this.form.address = '';
      }
    }
  };