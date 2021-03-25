<template>
  <div
      class="card"
      :class="{completed: todo.completed}"
      v-on:click="$emit('todoClick',todo.id)"
    >
    <strong>{{ todo.title }}</strong>

  </div>

</template>

<script>
export default {
  emits:['todoClick'],
  name: 'Todo',
  props: {
    todo: Object,
  }
};
</script>

<style>
.card {
  border-radius: 15px;
  background-color: #ececab;
  padding: 15px;
  margin: 10px;
}

.completed {
  background-color: #a19c9c;
  color: black;
}
strong{
  pointer-events: none;
}
</style>
