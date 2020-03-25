<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" placeholder="Add Todo..." />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
// import { v4 as uuidv4 } from "uuid";
export default {
  name: "AddTodo",
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        // id: uuidv4(),
        title: this.title,
        completed: false
      };
      this.$emit("add-todo", newTodo);

      this.title = "";
    }
  },
  data() {
    return {
      title: ""
    };
  }
};
</script>

<style scoped>
form {
  display: flex;
}

input[type="text"] {
  flex: 10;
  padding: 5px;
}

input[type="submit"] {
  flex: 2;
}
</style>