<template>
  <div class="home mt-5">
    <app-header></app-header>
    <div class="d-flex mb-4 mt-5 flex-column flex-md-row">
      <b-input
        v-on:keyup.enter="addTodo"
        v-model="todo"
        placeholder="Add todo's"
        class="mr-0 mr-md-4 mb-3 mb-md-0"
      ></b-input
      ><b-button @click="addTodo" variant="success">Add</b-button>
    </div>
    <todo-list @delete="deleteTodo" :todos="todos"></todo-list>
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import TodoList from '@/components/TodoList.vue'
export default {
  name: 'Home',
  components: {
    AppHeader,
    TodoList
  },
  data() {
    return {
      todo: '',
      todos: []
    }
  },
  methods: {
    addTodo() {
      if (!this.todo) return
      const todo = {
        id: this.todos.length + 1 + Math.floor(Math.random() * 100), // unreliable, but uuid is overkill
        label: this.todo,
        done: false
      }
      this.todos.push(todo)
      this.todo = ''
    },
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  }
}
</script>

<style lang="scss" scoped>
@import url('https://fonts.googleapis.com/css2?family=Fredericka+the+Great&display=swap');
</style>
