<template>
  <main>
    <form>
      <input type="text" v-model="name"/>
      <input type="email" v-model="email"/>
      <div @click="onSubmit">Add task</div>
      <div v-for="item in items" :key="item.id" style="display: flex; border: 1px solid #000; width: 200px;">
        <div style="margin-right: 15px">{{item.title}}</div>
        <div>{{item.description}}</div>
      </div>
    </form>
  </main>
</template>

<script>
import {reactive, toRefs, ref} from 'vue'
export default {
  name: 'App',
  setup() {
    const params = reactive ({
      name: "",
      email: ""
    })
    const items = ref([
      {
        title: "title",
        description: "description"
      },
      {
        title: "title-2",
        description: "description-2"
      },
      {
        title: "title-3",
        description: "description-3"
      },
      {
        title: "title-4",
        description: "description-4"
      },
    ])
    const onSubmit = () => {console.log(params.name, params.email)}
    return {
      ...toRefs(params),
      onSubmit,
      items
    } 
  }
}
</script>

<style scoped>
  .task-list {
    list-style: none;
  }
</style>