<template>
  <ul class="hello">
    <Todo @changeStatus="changeStatus" @deleteTask="deleteTask" v-for="todo in todos" :key="todo.id" :todo="todo" />
  </ul>
</template>

<script>
import Todo from './Todo'

export default {
  name: 'List',
  props: ['todos'],
  methods: {
      changeStatus(id) {
          this.$emit('changeStatus', id)
      },
      deleteTask(id){
        this.$emit('deleteTask', id)
      },
  },
  components: {
      Todo
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Quicksand:wght@300&display=swap');

  *{
    font-family: 'Quicksand', sans-serif;
  }
</style>