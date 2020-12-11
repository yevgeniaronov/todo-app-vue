<template>
  <div
    class="shadow p-3 mb-3 bg-white rounded d-flex justify-content-between align-items-center"
    :class="{ done: todo.done }"
  >
    <div class="d-flex">
      <b-form-checkbox
        button-variant="success"
        v-model="todo.done"
      ></b-form-checkbox>
      <span class="label">
        {{ todo.label }}
      </span>
    </div>
    <b-button
      class="trash-button"
      variant="link"
      @click="$emit('delete', todo.id)"
    >
      <font-awesome-icon icon="trash" />
    </b-button>
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  data() {
    return {}
  },
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
}
</script>

<style lang="scss" scoped>
.done {
  .label {
    color: #6b7176;
    text-decoration-line: line-through;
  }
}
</style>
