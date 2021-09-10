<template>
  <div class="task-input my-list">
    <input v-model="title" placeholder="Title" type="text">
  </div>
</template>

<script>
export default {
  props: {
    value: String
  },
  setup (props, {emit}) {
    const { input } = (
      props.value, 
      value => emit("input", value)
    );
    return {
      input
    }
  }
}
</script>

<style scoped>
.task-input {
  margin: 10px 0;
}
</style>
