<template>
    <div>
        <form @submit='addTodo'>
            <input v-model='title' type = 'text' name = 'title' placeholder = 'add-todo' />
            <input type = 'submit' value = 'Submit' class = 'btn' />
        </form>
    </div>
</template>

<script>
import uuid from 'uuid';
export default {
    name: 'AddTodo',
    data(){
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault();
            const newTodo = {
                title:this.title,
                completed: false
            }
            //SEND UP TO PARENT WITH EVENT
            this.$emit('add-todo', newTodo);

            this.title = ''
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
}

input[type='text']{
    flex: 20;
    padding: 10px;
}
input[type='submit']{
    flex: 3;
}
</style>