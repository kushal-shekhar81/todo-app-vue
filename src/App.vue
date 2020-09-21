<template>
  
  <div class="container">
    <Header />
    <AddTodo v-on:add-todo="addTodo" />
    <TodosList v-bind:todos="todos" v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>
import Header from './components/Layout/Header';
import TodosList from  './components/TodosList';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Header,
    AddTodo,
    TodosList
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: 'Todo one',
          completed: false
        },
        {
          id: 1,
          title: 'Todo two',
          completed: true
        },
        {
          id: 2,
          title: 'Todo three',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },

    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    }
  }
  
}
</script>

<style scoped>

</style>
