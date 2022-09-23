<template>
  <h1>{{ task.name }}</h1>
  <p>{{ task.description }}</p>
</template>

<script>
export default {
  name: 'MyTodo',
  props: {
    task: Object,
  },
  data() {
    return {};
  },
};
</script>

<style></style>
