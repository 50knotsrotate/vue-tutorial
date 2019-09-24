<template>
  <div id="app">
    <Header />
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <AddTodo v-on:add-todo="addTodo" />
    <Todos v-on:del-todo='deleteTodo' v-bind:todos="todos"/>
  </div>
</template>

<script>
import Todos from './components/Todos'
import Header from './components/layout/Header';
import AddTodo from './components/AddTodo'
import axios from 'axios';
export default {
  name: "app",
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: []
    };
  },
  methods: {
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo];
    }
  },
  created(){
    axios.get('https://jsonplaceholder.typicode.com/todos').then(res => {
      this.todos = res.data;
      console.log(res.data);
    }).catch(err => {
      console.log(error);
    })
  }
};
</script>

<style>
.btn {
  display: inline-block;
  border: none;
  background: #555;
  padding: #fff;
  padding: 7px 20px;
  cursor: pointer;
}
</style>
