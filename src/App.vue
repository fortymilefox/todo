<template>
  <div id="app">
    <md-field>
      <md-input v-model="currentTodo" @keydown.enter="addTodo()" placeholder="Add a todo"></md-input>
    </md-field>
    <ul class="todos">
      <li v-for="todo in todos" :key="todo.id">
        {{todo.label}}
      </li>
      <button v-for="todo in todos" :key="todo.id" @click="removeTodo(todo)">Delete</button>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      todos: [],
      currentTodo: '',
      editedToDoId: ''
    };
  },
  methods: {
    addTodo() {
      this.todos.push({id: this.todos.length, label: this.currentTodo, completed: false});
      this.currentTodo = '';
    },
    removeTodo(todo) {
      var index = this.todos.indexOf(todo);
      this.todos.splice(index, 1);
    },

  }
};
</script>

<style>
</style>
