<template>
  <div class="alert alert-secondary">{{ task.content }}</div>
</template>

<script>
export default {
  name: 'Task',
  props: {
    task: Object
  }
}
</script>

<style scoped></style>
