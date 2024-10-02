<template>
  <div id="app">
    <h3>Sở thích</h3>
    <div>
      <label>
        <input type="checkbox" value="Đá bóng" v-model="selectedHobbies" />
        Đá bóng
      </label>
      <label>
        <input type="checkbox" value="Bóng chuyền" v-model="selectedHobbies" />
        Bóng chuyền
      </label>
      <label>
        <input type="checkbox" value="Code" v-model="selectedHobbies" />
        Code
      </label>
      <label>
        <input type="checkbox" value="Bơi lội" v-model="selectedHobbies" />
        Bơi lội
      </label>
    </div>

    <div>
      <h4>Sở thích:</h4>
      <p>{{ selectedHobbies }}</p>
    </div>
  </div>
</template>

  <script setup>
new Vue({
  el: '#app',
  data: {
    selectedHobbies: []
  }
});
</script>

<style scoped>
label {
  display: block;
  margin-bottom: 10px;
}
</style>
