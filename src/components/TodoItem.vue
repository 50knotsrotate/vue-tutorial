<template>
  <div class = "todo-item" v-bind:class="{'is-complete': todo.completed}">
    <p>{{todo.title}}</p>
  </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"]
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