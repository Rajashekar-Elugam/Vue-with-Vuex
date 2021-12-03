<template>
  <div>
    <h1 class="title">Todos Application</h1>
    <div class="todo-count">
      <h3>Total: {{ totalTodos }}</h3>
      <h3 style="color: green">Completed: {{ completedTodos }}</h3>
      <h3 style="color: red">Pending: {{ pendingTodos }}</h3>
    </div>
    <div>
      <todos-list />
      <todo-form />
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

import TodosList from "./components/TodosList.vue";
import TodoForm from "./components/TodoForm.vue";

export default {
  name: "App",
  components: {
    TodosList,
    TodoForm,
  },

  computed: {
    // completedTodos() {
    //   return this.$store.getters.completedTodos;
    // },
    // pendingTodos() {
    //   return this.$store.getters.pendingTodos;
    // },
    // totalTodos() {
    //   return this.$store.getters.totalTodos;
    // },

    ...mapGetters({
      completedTodos: "completedTodos",
      pendingTodos: "pendingTodos",
      totalTodos: "totalTodos",
    }),
  },
};
</script>

<style>
#app {
  display: flex;
  justify-content: center;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.title {
  font-style: italic;
  color: blueviolet;
  text-decoration: underline;
}

.todo-count {
  display: flex;
  justify-content: space-between;
}
</style>
