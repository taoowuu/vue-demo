<template>
  <div class="test">
    <h1>{{ msg }}</h1>
    <input >
    <button v-on:click='addTodo'>add</button>
    <br>

  </div>
</template>

<script>
export default {
  name: 'Todo',
  data() {
    return {
      msg: 'Todo',
    }
  },
  methods: {
    addTodo: function() {
      console.log('add')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .test {
    text-align: center;
  }
</style>
