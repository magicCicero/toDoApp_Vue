<template>
  <div class="alert" :class="alertClass">{{ task.content }}</div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object,
    alertColor: {
      type: String,
      default: 'secondary'
    }
  },
  computed: {
    alertClass() {
      return 'alert-' + this.alertColor
    }
  }
}
</script>

<style scoped></style>
