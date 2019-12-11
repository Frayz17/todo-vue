<template>
  <div class="collection-item">
    <div class="item-wrapper" v-on:click="toggleComplete">
      <p v-bind:class="{ 'is-complete': todo.completed }">{{ todo.title }}</p>
      <button
        @click="$emit('del-todo', todo.id)"
        class="btn-floating btn-small waves-effect waves-light red"
      >
        x
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    toggleComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
.item-wrapper {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.is-complete {
  text-decoration: line-through;
}
</style>
