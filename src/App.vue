<template>
  <div class="container mt-5">
    <div class="row">
      <div class="col-4" v-for="statusCard in statusCards" :key="statusCard.status">
        <StatusCard
          :title="statusCard.title"
          :titleClasses:="statusCard.titleClasses"
          :newTasks="statusCard.newTasks"
          :status="statusCard.status"
          :tasks="filteredTasks(statusCard.status)"
        />
      </div>
    </div>
  </div>
</template>

<script>
import StatusCard from './components/StatusCard.vue'
export default {
  name: 'App',
  components: {
    StatusCard
  },
  data() {
    return {
      tasks: [
        {
          id: 1,
          content: 'Dashboard überarbeiten.',
          status: 0
        },
        {
          id: 2,
          content: 'Anwendung auf Vue.js umstellen.',
          status: 0
        }
      ],
      statusCards: [
        {
          title: 'Neue Aufgaben',
          titleClasses: 'bg-secondary text-white',
          newTasks: true,
          status: 0
        },
        {
          title: 'in Bearbeitung',
          titleClasses: 'bg-primary text-white',
          newTasks: false,
          status: 1
        },
        {
          title: 'Erledigt',
          titleClasses: 'bg-success text-white',
          newTasks: false,
          status: 2
        }
      ]
    }
  },
  // computed: {
  //   newTasks() {
  //     return this.tasks.filter((task) => task.status === 0)
  //   }
  // }
  methods: {
    filteredTasks(status) {
      return this.tasks.filter((task) => task.status === status)
    }
  }
}
</script>

<style></style>
