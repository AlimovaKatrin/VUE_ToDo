<template>
  <div >
      <Todo v-for="todo in list" :key="todo.id" :todo="todo"/>
  </div>
</template>

<script>
import Todo from './Todo';

export default {
  name: 'List',
  props: {
    list: Array
  },
  components: {
    Todo
  }

};
</script>

