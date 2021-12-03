<template>
  <div>
    <input type="text" placeholder="Enter new todo" v-model="newTodoItem" />
    <br />
    <button @click="addNewTodoItem()">Submit</button>
  </div>
</template>

<script>
export default {
  name: "TodoForm",
  data() {
    return {
      newTodoItem: "",
    };
  },

  methods: {
    addNewTodoItem() {
      if (this.newTodoItem.length > 0) {
        this.$store.dispatch("addNewTodo", this.newTodoItem);
        this.newTodoItem = "";
      }
    },
  },
};
</script>

<style scoped>
input {
  width: 184px;
  height: 24px;
  border-radius: 4px;
  margin-bottom: 5px;
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
