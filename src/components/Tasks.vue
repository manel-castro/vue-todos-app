<template>
  <div v-for="(task) in tasks" :key="task.id">
    <Task @toggle-reminder="id => $emit('toggle-reminder', id)" @delete-task="id => $emit('delete-task',id)" :task="task" />
  </div>
</template>

<script>
  import Task from './Task.vue'

  export default {
    name: 'Tasks',
    props: {
      tasks: Array,
    },
    components: {
      Task,
    },
    emits: ['delete-task', 'toggle-reminder']
  }
</script>