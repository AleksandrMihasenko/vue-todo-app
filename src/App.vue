<template>
    <div id="app">
        <Header></Header>
        <AddTodo v-on:add-todo="addTodo"></AddTodo>
        <Todos v-bind:todoList="todos" v-on:del-todo="deleteTodo"></Todos>
    </div>
</template>

<script>
import Header from "@/components/layout/Header";
import Todos from './components/Todos';
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

<style>
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }

    body {
        font-family: Arial, Helvetica, sans-serif;
        line-height: 1.4;
    }

    .btn {
        display: inline-block;
        border: none;
        background: #555;
        color: #fff;
        padding: 7px 20px;
        cursor: pointer;
    }

    .btn:hover {
        background: #666;
    }
</style>
