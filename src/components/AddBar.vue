<template>
  <div class="add-bar">
    <input type="text" class="add" placeholder="What needs to be done?" @keyup="addList" v-model="todo">
  </div>
</template>

<script>
export default {
  data() {
    return {
      todo: ""
    }
  },
  methods: {
    addList(e) {
      if (e.keyCode == 13 && this.todo) {
        this.$emit('addTodo', this.todo);
        this.todo = '';
      }
    }
  }
}
</script>

<style lang="scss">
.add-bar {
  width: 80%;
  height: 3rem;
  margin: 5% auto;
  background: #fff;
  .add {
    height: 100%;
    width: 100%;
    border: 0px;
    font-size: 2rem;
    outline: none;
  }
}
</style>
