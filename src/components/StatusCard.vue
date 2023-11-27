<template>
  <div class="card">
    <div class="card-header text-center" :classes="titleClasses">
      <h4>{{ title }}</h4>
    </div>
    <div class="card-body">
      <Task v-for="task in tasks" :key="task.id" :task="task" />
    </div>
    <div class="card-footer" v-if="newTasks">
      <NewTask />
    </div>
  </div>
</template>

<script>
import Task from './Task.vue'
import NewTask from './NewTask.vue'
export default {
  name: 'StatusCard',
  components: {
    Task,
    NewTask
  },
  props: {
    title: String,
    titleClasses: String,
    status: Number,
    newTasks: Boolean,
    tasks: Array
  }
}
</script>

<style scoped></style>
