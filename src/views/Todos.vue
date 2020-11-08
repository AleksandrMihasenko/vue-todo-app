<template>
    <div>
        <Header></Header>
        <router-link class="link" to="/">Home page</router-link>
        <AddTodo v-on:add-todo="addTodo"></AddTodo>
        <Todos v-if="todos.length" v-bind:todoList="todos" v-on:del-todo="deleteTodo"></Todos>
        <p v-else>No todos</p>
    </div>
</template>



<script>
import Header from "@/components/layout/Header";
import Todos from '@/components/Todos';
import AddTodo from "@/components/AddTodo";

export default {
    name: 'App',
    components: {
        Todos,
        AddTodo,
        Header
    },
    data() {
        return {
            todos: []
        }
    },
    methods: {
        deleteTodo(id) {
            this.todos = this.todos.filter(todo => todo.id !== id);
        },
        addTodo(newTodo) {
            this.todos = [...this.todos, newTodo];
        }
    },
    created() {
        fetch('https://jsonplaceholder.typicode.com/todos?_limit=3')
        .then(response => response.json())
        .then(json => {
            this.todos = json;
        });
    }
}
</script>

<style scoped>
    .link {
        display: flex;
        justify-content: center;
        margin: 5px;
    }
</style>
