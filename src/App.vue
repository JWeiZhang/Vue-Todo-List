<template>
  <div id="app">
    <div class="main">
      <div class="title">Todos</div>
      <add-bar @addTodo="addTodo"></add-bar>
      <div class="todo-container">
        <todo v-for="(item, index) in todoList" :key="index" :todo="item"></todo>
      </div>
    </div>
    <!-- <router-view/> -->
  </div>
</template>

<script>
import AddBar from './components/AddBar.vue'
import Todo from './components/Todo.vue'
export default {
  name: 'App',
  components: {
    AddBar,
    Todo
  },
  data() {
    return {
      todoList: []
    }
  },
  methods: {
    addTodo(val) {
      this.todoList.push({ name: val, status: 0 });
    }
  }
}
</script>

<style lang="scss">
@import url(//fonts.googleapis.com/earlyaccess/notosanstc.css);
#app {
  font-family: "Noto Sans TC", "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.main {
  width: 30%;
  height: 80vh;
  margin: 0 auto;
  background: #d2d2d2d2;
  box-shadow: 5px 10px 8px #888888;
  .title {
    background: #5599ff;
    height: 3rem;
    text-align: center;
    line-height: 3rem;
    font-size: 2em;
    font-weight: 600;
  }
  .todo-container {
    width: 80%;
    margin: 0 auto;
    height: 60%;
    overflow: auto;
  }
}
</style>
