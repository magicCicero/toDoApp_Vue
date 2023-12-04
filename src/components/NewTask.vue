<template>
  <div>
    <input type="text" class="form-control" placeholder="Neue Aufgabe" v-model="content" />
    <div class="d-grid my-2">
      <button class="btn btn-secondary" @click="submitTask()">Eintragen</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewTask',
  emits: {
    'new-tasks': (task) => {
      if (task.content === '') {
        console.warn('NewTaskComponent:Der Content sollte nicht leer sein.')
        return false
      }
      return true
    }
  },
  data() {
    return {
      content: ''
    }
  },
  methods: {
    submitTask() {
      this.$emit('new-task', {
        //payload
      })
    }
  }
}
</script>

<style scoped></style>
