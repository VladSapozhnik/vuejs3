<template>
  <div class="task-card my-style">
      <input v-model="email" placeholder="Description" type="email">
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
.task-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
</style>