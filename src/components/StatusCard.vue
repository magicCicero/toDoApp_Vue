<template>
  <div class="card">
    <div class="card-header text-center" :classes="titleClasses">
      <h4>{{ title }}</h4>
    </div>
    <div class="card-body">
      <Task v-for="task in tasks" :key="task.id" :task="task" :alertColor="alertColor" />
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
  },
  computed: {
    alertColor() {
      switch (this.status) {
        case 0:
          return 'secondary'
        case 1:
          return 'primary'
        case 2:
          return 'success'
      }
      return 'danger'
    }
  }
}
</script>

<style scoped></style>
