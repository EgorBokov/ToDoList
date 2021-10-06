<template>
  <div class="hello">
    <input @input="func" />
    <h2 class="example">Example2272</h2>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld2',
  methods: {
    func(event) {
      this.$emit('changeName', event.target.value)
    }
  }
}
</script>

<style scoped>
.title {
  background: blue;
  color: red
}
</style>

<style>
*{
font-family: 'Comic Sans MS';
}
</style>