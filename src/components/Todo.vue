<template>
    <div class="todo" @click="changeStatus" :class="{'del': todo.status}">
        <font-awesome-icon :icon="todo.status ? ['far','check-circle'] : ['far','circle']" />
        <!-- <span>{{ todo.name }}</span> -->
        <input type="text" v-model="todo.name" :readonly="!isModifying">
        <font-awesome-icon class="del-icon " :icon="[ 'far', 'trash-alt'] " @click="delTodo " />
    </div>
</template>

<script>
export default {
    props: ['todo'],
    data() {
        return {
            isModifying: false
        }
    },
    methods: {
        changeStatus() {
            this.$emit("changeStatus", this.todo);
        },
        delTodo() {
            this.$emit("delTodo", this.todo);
        }
    }
}
</script>

<style lang="scss">
.todo {
  background: #fff;
  height: 3rem;
  font-size: 2rem;
  border-bottom: 1px solid #d2d2d2d2;
  text-align: left;
  padding-left: 0.7rem;
  position: relative;
  input {
    border: none;
    color: #2c3e50;
    font-size: 2rem;
    width: 70%;
  }
  .del-icon {
    position: absolute;
    right: 0.7rem;
    top: 0.6rem;
    cursor: pointer;
    color: #fff;
    transition: all 0.2s ease-out;
    &:hover {
      color: #2c3e50;
    }
  }
}
.del {
  input {
    text-decoration: line-through;
    color: #d2d2d2d2;
    transition: all 0.2s ease-out;
  }
}
</style>
