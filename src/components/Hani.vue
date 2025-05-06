<template>
  <div class="app-container">
    <div class="todo-container">
      <h1>Daftar Bunga🌷</h1>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Cal+Sans&family=Poppins:wght@300;400;500;600&display=swap');

* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: "Poppins", sans-serif;
  background-color: #85a5e1;
}

.app-container {
  background-color: #b5d0fc;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.todo-container {
  background-color: #f0f4ff;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  text-align: center;
  width: 100%;
  max-width: 500px;
  border: 4px solid #b6c7ff;
}

h1 {
  font-family: "Cal Sans", sans-serif;
  font-size: 35px;
  color: #4176e8;
  margin-bottom: 20px;
}
</style>