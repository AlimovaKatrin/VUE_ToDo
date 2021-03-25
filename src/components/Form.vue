<template>
  <form @submit.prevent="$emit('addTodo',title)">
    <input v-model="title" name="title"/>
    <button>
      Add
    </button>
  </form>
</template>

<script>
export default {
  name: 'Form',
  emits: [ 'addTodo' ],
  data () {
    return {
      title: null
    };
  }
};
</script>

<style>
form {
  border-radius: 15px;
  background-color: #2c3e50;
  padding: 15px;
}

form > input {
  border-radius: 5px;
  padding: 5px;
}

form > button {
  border-radius: 5px;
  padding: 5px;
  margin: 5px;
  background-color: white;
  transition: all 0.5s ease-in-out;
}

form > button:hover {
  background-color: #5dc080;
  transform: scale(1.1);
}
</style>
