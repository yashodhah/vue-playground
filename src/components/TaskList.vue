<template>
  <div :key="task.id" v-for="task in tasks">
    <Task
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      @delete-task="$emit('delete-task', task.id)"
      :taskDetails="task"
    ></Task>
  </div>
</template>

<script>
import Task from './Task';
export default {
  name: 'TaskList',
  components: { Task },
  props: {
    tasks: Array,
  },
  emits: ['delete-task', 'toggle-reminder'],
};
</script>

<style scoped></style>
