<template>
  <div>
    <form @submit="addTask">
      <input type="text" v-model="title" name="title">
      <button type="submit">Add</button>
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
  name: "add-task",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTask(item) {
      item.preventDefault();
      const newTask = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }
      this.$emit('add-task', newTask);
      this.title = '';
    }
  }
}
</script>

<style scoped>

</style>
