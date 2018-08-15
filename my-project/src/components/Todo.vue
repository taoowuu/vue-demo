<template>
  <div class="test">
    <h1>Todo</h1>
    <input v-model='newTodo'>
    <button v-on:click='addTodo'>add</button>
    <br>
    <ul>
      <li v-for='todo in todos'>
        <input type="checkbox" v-bind:class='toggle' v-model='todo.done'>
        <span v-bind:class='{done: todo.done}'>
          {{ todo.task }}
        </span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  data() {
    return {
      todos: [
        {
          task: '1',
          done: false,
        },
      ],
      newTodo: '',
    }
  },
  methods: {
    addTodo: function() {
      // console.log('add')
      // this.todos.push(this.newTodo)
      this.todos.push({
        task: this.newTodo,
        done: false,
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .test {
    text-align: center;
  }
  .done {
    text-decoration: line-through;
  }
</style>
