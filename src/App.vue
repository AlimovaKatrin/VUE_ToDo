<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <List :list="list" :switchStatus="switchStatus"/>
  </div>
</template>

<script>
import List from './components/List.vue'

export default {
  name: 'App',
  data(){
    return {
    list:[{
      title:'Walk granny',
      completed: false,
      id:0
    }]
    }
  },
  methods:{
    switchStatus(index){
      this.list[index].completed = !this.list[index].completed
    }
  },
  beforeCreate () {
    fetch('https://jsonplaceholder.typicode.com/todos')
        .then(response => response.json())
        .then(json => this.list = [...this.list,...json])
  },
  components: {
    List
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
