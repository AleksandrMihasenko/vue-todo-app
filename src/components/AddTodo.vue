<template>
    <div>
        <form v-on:submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add todo">
            <input type="submit" value="Create" class="btn">
        </form>
    </div>
</template>

<script>

export default {
    name: 'AddTodo',
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(event) {
            event.preventDefault();

            const newTodo = {
                id: Date.now(),
                title: this.title,
                completed: false
            }

            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
    }

    input[type="text"] {
        flex: 10;
        padding: 5px;
    }

    input[type="submit"] {
        flex: 2;
    }
</style>
