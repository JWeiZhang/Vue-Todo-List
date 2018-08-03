<template>
    <div class="todo">
        <font-awesome-icon :icon="['far','circle']" /> {{ todo.name }}
    </div>
</template>

<script>
export default {
    props: ['todo']
}
</script>

<style lang="scss">
.todo {
  background: #fff;
  height: 3rem;
  font-size: 2rem;
  border-bottom: 1px solid #d2d2d2d2;
}
</style>
