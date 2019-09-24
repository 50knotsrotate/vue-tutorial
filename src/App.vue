<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Todos v-on:del-todo='deleteTodo' v-bind:todos="todos"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
export default {
  name: "app",
  components: {
    Todos
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Todo one",
          completed: false
        },
        {
          id: 2,
          title: "Todo two",
          completed: false
        },
        {
          id: 3,
          title: "Take out trash",
          complted: false
        },
        {
          id: 4,
          title: "Walk dogs",
          complted: false
        },
        {
          id: 5,
          title: "Go to work",
          completed: false
        },
        {
          id: 6,
          title:'Drive home',
          completed: false
        }
      ]
    };
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
