<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>Essential Links</h2>
    <ul>
      <li><a href="https://vuejs.org" target="_blank">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank">Forum</a></li>
      <li><a href="https://gitter.im/vuejs/vue" target="_blank">Gitter Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank">Twitter</a></li>
      <br>
      <li><a href="http://vuejs-templates.github.io/webpack/" target="_blank">Docs for This Template</a></li>
    </ul>
    <h2>Ecosystem</h2>
    <ul>
      <li><a href="http://router.vuejs.org/" target="_blank">vue-router</a></li>
      <li><a href="http://vuex.vuejs.org/" target="_blank">vuex</a></li>
      <li><a href="http://vue-loader.vuejs.org/" target="_blank">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank">awesome-vue</a></li>
    </ul>
    <button @click="changeTitle">Change title</button>
    <p>{{ title }}</p>

    <input type=text v-on:input="cssClass = $event.target.value"/>
    <p v-bind:class="cssClass">{{ cssClass }}</p>

    <button @click="increment">Increment</button> {{ counter }}

    <p v-if="show">This is just some test</p>
    <p v-else>This is another test</p>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      title: 'Not clicked',
      cssClass: '',
      clicked: false,
      counter: 0,
      show: true
    }
  },
  methods: {
    changeTitle() {
      this.clicked = !this.clicked,
      this.title = this.clicked? 'Changed!' : 'Unchanged!'
    },
    increment() {
      this.counter++;
      this.show = !this.show;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}

.red {
  background-color: red;
}

.blue {
  background-color: blue;
}
</style>
