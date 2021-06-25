<template>
  <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
    <h3>{{ task.text }}
      <i @click="onDelete(task.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
  export default {
    name: 'Task',
    props: {
      task: Object,
    },
    methods: {
      onDelete(id) {
        // console.log(id);
        this.$emit('delete-task', id)
      }
    },
    // emits: ['delete-task']
  }
</script>

<style scope>
  .fas {
    color: red;
  }

  .div { /* since scoped we just have one div into this component */ 
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
  }

  .task.reminder { /* if the reminder is set to true we'll have a green border */ 
    border-left: 5px solid green;
  }

  .task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }

</style>