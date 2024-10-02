<template>
  <div>
    <h2>Thêm sản phẩm mới</h2>
    <form @submit.prevent="submitForm">
      <div>
        <label for="productCode">Mã sản phẩm:</label>
        <input type="text" id="productCode" v-model="product.productCode" />
      </div>
      <div>
        <label for="productName">Tên sản phẩm:</label>
        <input type="text" id="productName" v-model="product.productName" />
      </div>
      <div>
        <label for="price">Giá:</label>
        <input type="number" id="price" v-model="product.price" />
      </div>
      <div>
        <label for="quantity">Số lượng:</label>
        <input type="number" id="quantity" v-model="product.quantity" />
      </div>
      <button type="submit">Thêm mới</button>
    </form>
  </div>
</template>

<script setup>
import { reactive } from 'vue';

const product = reactive({
  productCode: '',
  productName: '',
  price: null,
  quantity: null,
});

const submitForm = () => {
  console.log(product);
};
</script>

<style scoped>
</style>
