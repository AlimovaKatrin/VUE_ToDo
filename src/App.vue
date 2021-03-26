<template>
  <div id="app">
    <div id="form-container">
      <img alt="Vue logo" src="./assets/logo.png">
      <Form v-on:addTodo="addTodo"/>
    </div>

    <List :list="list" v-on:todoClick="switchStatus"/>
  </div>
</template>

<script>
import List from './components/List.vue';
import Form from './components/Form';

export default {
  name: 'App',
  data () {
    return {
      list: [ {
        title: 'Walk granny',
        completed: false,
        id: 0
      } ]
    };
  },
  methods: {
    switchStatus ( id ) {
      let index;
      this.list.forEach((el,i) => {
        if(el.id === id){
         index = i;
        }
      });
      if(index >= 0){
        this.list[index].completed = !this.list[index].completed;
      }
    },
    addTodo ( title ) {
      const todo = {
        title,
        completed: false,
        id: this.list.length
      };
      this.list = [ todo, ...this.list ];
    }
  },
  beforeCreate () {
    fetch('https://jsonplaceholder.typicode.com/todos')
        .then(response => response.json())
        .then(json => this.list = [ ...this.list, ...json ]);
  },
  components: {
    List,
    Form
  }
};
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

#form-container {
  display: flex;
  align-items: center;
  justify-content: center /*flex-direction: ;*/
}
</style>
