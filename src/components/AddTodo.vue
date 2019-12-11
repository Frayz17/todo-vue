<template>
  <div class="row">
    <form @submit="addTodo" class="col s12">
      <div class="row">
        <div class="input-field col m10 s12">
          <input
            type="text"
            v-model="title"
            name="title"
            placeholder="Add Todo..."
          />
        </div>
        <div class="input-field col m2 s3">
          <button
            class="waves-effect waves-light btn green darken-4"
            type="submit"
          >
            Submit
          </button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'AddTodo',
  data() {
    return {
      title: ''
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();

      const newTodo = {
        title: this.title,
        completed: false
      };
      this.$emit('add-todo', newTodo);

      this.title = '';
    }
  }
};
</script>

<style scoped>
/* form {
  display: flex;
} */

/* .input-field {
  flex: 10;
  padding: 5px;
} */

/* input[type='submit'] {
  flex: 2;
} */
</style>
