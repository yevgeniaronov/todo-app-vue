<template>
  <div v-if="todos.length">
    <todo-item
      :todo="todo"
      v-for="todo in todos"
      :key="todo.id"
      @delete="$emit('delete', todo.id)"
    >
    </todo-item>
  </div>
  <div v-else>
    <h2>No Todo’s to show...</h2>
  </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
export default {
  name: 'TodoList',
  components: {
    TodoItem
  },
  props: {
    todos: {
      type: Array,
      required: true
    }
  },
  data() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
h2 {
  font-family: 'Fredericka the Great', cursive;
  font-size: 24px;
}
</style>
