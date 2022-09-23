<template>
  <MyHeader />
  <ResultSlot />
  <MyTodo v-for="task in tasks" :key="task.id" :task="task" />

  <form>
    <label>Name</label>
    <input type="text" v-model="taskName" />
    <label>Description</label>
    <input type="text" v-model="taskDescription" />
    <button @click="addTask">Add task</button>
  </form>
  <MyFooter />
</template>

<script>
import MyHeader from './components/MyHeader.vue';
import ResultSlot from './components/ResultSlot.vue';
import MyTodo from './components/MyTodo.vue';
import MyFooter from './components/MyFooter.vue';

export default {
  name: 'App',
  components: {
    MyHeader,
    ResultSlot,
    MyTodo,
    MyFooter,
  },
  data() {
    return {
      taskName: '',
      taskDescription: '',
      tasks: [
        { id: 1, name: 'Cooking', description: 'Roast chicken' },
        { id: 2, name: 'Cleaning', description: 'Clean bathroom' },
      ],
    };
  },
  methods: {
    addTask() {
      let task = {
        id: this.tasks.length + 1,
        name: this.taskName,
        description: this.taskDescription,
      };
      console.log(task);
      this.tasks.push(task);
      console.log(this.tasks);
    },
  },
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
</style>
