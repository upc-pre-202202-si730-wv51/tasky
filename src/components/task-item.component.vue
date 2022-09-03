<template>
  <div v-bind:class="{ 'completed': task.completed }">
    <p v-on:click="markComplete">
      {{ task.title }}
    </p>
    <button @click="$emit('delete-task', task.id)">Delete</button>
  </div>
</template>

<script>
export default {
  name: "task-item",
  props: [
      "task"
  ],
  methods: {
    markComplete() {
      this.task.completed = !this.task.completed;
    }
  }
}
</script>

<style scoped>
  .completed {
    text-decoration: line-through;
  }
</style>
