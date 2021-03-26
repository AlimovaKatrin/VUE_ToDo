<template>
  <div class="container">
      <Todo
          v-for="todo in list"
          :key="todo.id"
          :todo="todo"
          v-on:todoClick="$emit('todoClick', $event)"
      />
    <!--          v-on:todoClick="switchStatus"-->

  </div>
</template>

<script>

import Todo from './Todo';

export default {
  name: 'List',
  props: {
    list: Array,
    // switchStatus:Function
  },
  components: {
    Todo
  },

};
</script>
<style>
.container{
  display: flex;
  background-color: lightgray ;
  border-radius: 15px;
  max-width: 70vw;
  flex-wrap: wrap;
  margin:auto;
  padding: 15px;
  justify-content: space-around;
}

</style>
