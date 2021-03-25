<template>
  <div>
    <strong>{{ todo.title }}</strong>
  </div>

</template>

<script>
export default {
  name: 'Todo',
  props: {
    todo: Object
  }
};
</script>
