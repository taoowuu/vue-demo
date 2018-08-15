<template>
  <div class="test">
    <h1>{{ msg }}</h1>
    <span v-html="title"></span>
    <p v-if='showGender'>{{ user.gender }}</p>
    <p v-else>{{ user.name }}</p>
    <ul>
      <li v-for='a in all'>{{ a.title }}</li>
    </ul>
    <input type="text" v-model='input'>
    <h1>{{ input }}</h1>
    <button v-on:click='greet'>点击事件</button>
    <input v-on:keyup='pressKey' v-on:keyup.enter='hitEnter'>
    <br>
    <label>lastNmae: </label><input v-model='lastNmae'>
    <br>
    <label>firstNmae: </label><input v-model='firstNmae'>
    <h1>计算属性 computed 显示{{ fullName }}</h1>
    <h1>{{ m }}</h1>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    m: {
      default: '子组件默认内容',
      type: String,
    }
  },
  data () {
    return {
      msg: '{{}} 绑定数据',
      title: '<h2>v-html 显示</h2>',
      user: {
        name: 'v-if 选择性显示',
        gender: 'male',
      },
      showGender: false,
      all: [
        {title: 'v-for 输出'},
        {title: '1'},
        {title: '2'}
      ],
      input: 'v-model 热更新',
      lastNmae: 'Wu',
      firstNmae: 'Tao',
    }
  },
  methods: {
    greet: function() {
      alert('v-on:click 绑定事件')
    },
    pressKey: function(e) {
      console.log('keyup 事件', e.target.value)
    },
    hitEnter: function() {
      console.log('按下 enter 触发 v-on:keyup.enter 事件')
    }
  },
  computed: {
    fullName: function() {
      return this.lastNmae + this.firstNmae
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
