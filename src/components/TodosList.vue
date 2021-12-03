<template>
  <div>
    <todo v-for="(todo, index) in todos" :key="index + 1" :todo="todo" />
  </div>
</template>

<script>
import { mapState } from "vuex";

import Todo from "./Todo.vue";

export default {
  name: "TodosList",

  components: {
    Todo,
  },

  computed: {
    // todos() {
    //   return this.$store.state.todos;
    // },

    ...mapState({
      todos: "todos",
    }),
  },
};
</script>

<style scoped>
div {
  align-items: center;
  border: 2px solid lightseagreen;
  border-radius: 10px;
  margin-bottom: 10px;
  width: 300px;
  padding: 10px;
}
</style>
