<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todoList">
            <TodoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"></TodoItem>
        </div>
    </div>
</template>

<script>
import TodoItem from "@/components/TodoItem";

export default {
    name: 'Todos',
    components: {
        TodoItem
    },
    props: ['todoList']
}
</script>

<style scoped>

</style>
