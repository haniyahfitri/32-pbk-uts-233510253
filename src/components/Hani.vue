<template>
  <div class="app-container">
    <div class="todo-container">
<h1>Daftar Bunga🌷</h1>

      <div class="input-section">
        <input
          type="text"
          v-model="newTodo"
          placeholder="Tambahkan bunga!📬"
        />
        <button @click="addTodo">Tambah</button>
      </div>
      <ul>
        <li v-for="todo in todos" :key="todo.id" :class="{ done: todo.completed }">
          <input type="checkbox" v-model="todo.completed" />
          <span>{{ todo.text }}</span>
          <button class="delete-btn" @click="removeTodo(todo)">❌</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newTodo: '',
      todos: []
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo.trim()) {
        this.todos.push({
          id: Date.now(),
          text: this.newTodo,
          completed: false
        });
        this.newTodo = '';
      }
    },
    removeTodo(todo) {
      this.todos = this.todos.filter(t => t.id !== todo.id);
    }
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
.input-section {
  display: flex;
  justify-content: center;
  gap: 10px;
  margin-bottom: 20px;
  width: 100%;
  flex-wrap: wrap;
}

.input-section input[type="text"] {
  flex: 1;
  max-width: 350px;
  padding: 12px 15px;
  font-size: 16px;
  border: 2px solid #99b1ff;
  border-radius: 8px;
  background-color: #ffffff;
  font-family: "Poppins", sans-serif;
}

.input-section button {
  padding: 12px 20px;
  font-size: 16px;
  border-radius: 8px;
  background-color: #66b0ff;
  color: white;
  border: none;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s;
  font-family: "Poppins", sans-serif;
}

.input-section button:hover {
  background-color: #5a9ae3;
}
ul {
  list-style: none;
  padding: 0;
  margin-top: 10px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

li {
  font-family: "Poppins", sans-serif;
  background-color: #e6eeff;
  padding: 10px 15px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  border-radius: 8px;
  font-size: 16px;
  color: #3367d6;
  font-weight: bold;
}

li span {
  flex-grow: 1;
  text-align: left;
}
/* Tambahkan style untuk checkbox dan item selesai */
li input[type="checkbox"] {
  margin-right: 10px;
}

li.done span {
  text-decoration: line-through;
  color: gray;
  opacity: 0.7;
}
/* Tambahkan style untuk tombol hapus */
.delete-btn {
  background-color: #a3bef9;
  border: none;
  color: white;
  cursor: pointer;
  padding: 5px 10px;
  border-radius: 5px;
  font-size: 16px;
}

.delete-btn:hover {
  background-color: #8ba9e2;
}
</style>