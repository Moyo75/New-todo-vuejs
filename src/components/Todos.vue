<template>
  <section id="todos">
    <div class="todo" v-for="(todo) in todos" v-bind:key="todo.id">
      <input type="checkbox" name="done" v-if="todo.done" checked>
      <input type="checkbox" name="done" v-else>
      <label for="done">{{todo.name}}</label>
      <button class="remove" v-on:click="() => removeTodo(todo.id)">Remove</button>
    </div>
  </section>
</template>


<script>
export default {
  name: "Todos",
  props: ["todos"],
  methods: {
    removeTodo: function(id) {
      this.$emit("removeTodo", id);
    }
  }
};
</script>

<style scoped>
#todos {
  display: flex;
  flex-direction: row;
  justify-content: right;
  flex-wrap: wrap;
  width: 100%;
}

#todos > .todo {
  width: 24%;
  margin: 15px;
  /* text-transform: uppercase; */
  background: white;
  padding: 15px;

  display: flex;
}

.todo > label {
  flex: 1;
}
</style>
