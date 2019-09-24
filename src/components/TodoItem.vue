<template>
  <div class = "todo-item" v-bind:class="{'is-complete': todo.completed}">
    <p>{{todo.title}}</p>
    <input type = 'checkbox' v-on:change="markCompleted" />
    <button @click="$emit('del-todo', todo.id)" class = 'del'>X</button>
  </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markCompleted(){
            this.todo.completed = !this.todo.completed
        }
    }
};
</script>


<style scoped>
.todo-item {
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px solid black;
}

.todo-item:hover {
    background-color: lightgray;
}

.is-complete {
  text-decoration: line-through;
}

.del {
  background: red;
  color: #fff;
  padding: 5px 9px;
  border-radius: 5px;
  cursor: pointer;
  float: right;
}
</style>