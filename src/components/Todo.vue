<template>
  <div class="styles">
    <!-- <span class="todo-title" :class="{ completed: todo.completed }" @click="toggleTodoStatus">{{ todo.title }}</span>
    <button @click="deleteTodoItem">Delete</button> -->
    <span class="todo-title" :class="{ completed: todo.completed }" @click="toggleTodoStatus(todo)">{{ todo.title }}</span>
    <button @click="deleteTodo(todo)">Delete</button>
  </div>
</template>

<script>
import { mapActions } from "vuex";

export default {
  name: "Todo",
  props: ["todo"],

  methods: {
    // deleteTodoItem() {
    //   this.$store.dispatch("deleteTodo", this.todo);
    // },
    // toggleTodoStatus() {
    //   this.$store.dispatch("toggleTodoStatus", this.todo);
    // },

    ...mapActions({
      deleteTodo: "deleteTodo",
      toggleTodoStatus: "toggleTodoStatus",
    }),
  },
};
</script>

<style scoped>
.styles {
  height: 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 275px;
  margin: 5px auto;
  border: 2px solid black;
  border-radius: 5px;
  padding: 6px;
}

.completed {
  text-decoration: line-through;
}

.todo-title {
  font-weight: 500;
  color: chocolate;
}

button {
  width: 80px;
  height: 30px;
  color: antiquewhite;
  background-color: lightseagreen;
  border-radius: 3px;
  border-width: 2px;
  box-shadow: 5px 5px 5px rgba(100, 10, 0, 0.3);
  border-bottom-color: red;
  border-right-color: red;
  font-size: 16px;
}
</style>
