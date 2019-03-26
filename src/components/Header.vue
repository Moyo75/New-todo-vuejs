<template>
  <header>
    <input type="text" name="todoInput" v-model="todoValue" placeholder="What's the plan, Genius?">
    <button class="submit" v-on:click="createTodo">+</button>
  </header>
</template>

<script>
export default {
  name: "Header",
  data: function() {
    return {
      todoValue: ""
    };
  },
  methods: {
    createTodo: function() {
      this.$emit("createTodo", this.todoValue);
      this.todoValue = "";
    }
  }
};
</script>

<style scoped>
header {
  display: flex;
}

header > input {
  flex: 1;
  height: 35px;
  text-indent: 15px;
  box-sizing: border-box;
  font-size: 20px;
}

header > .submit {
  width: 50px;
  height: 35px;
  font-size: 24px;
  /* font-weight: 700; */
  outline: none;
  color: white;
  background-color: #59ec59;
  border: none;
  cursor: pointer;
}

header > .submit:hover {
  background-color: #51e251;
}

header > .submit:active {
  background-color: #50cf50;
}
</style>


