<template>
  <div class="hello">
    <input @input="func" />
    <button @click="func">button</button>
    <h2 class="example">Example227</h2>
    <h3> {{ rofl }} </h3>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  mounted() {
    console.log(this.$parent)
  },
  props: {
      rofl: String,
    },
  methods: {
    func(e) {
      // this.$emit('changeName', event.target.value)
      console.log(e.target.tagName)
    },
  },
  data() {
      return{
        prikol: 'Здарова!',
      };
  },
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
font-family: 'Times New Roman';
}

</style>