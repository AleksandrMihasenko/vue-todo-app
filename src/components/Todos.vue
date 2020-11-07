<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todoList">
            <h3>{{todo.title}}</h3>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Todos',
    props: ['todoList']
}
</script>

<style scoped>

</style>
