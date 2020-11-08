<template>
    <div class="home-page">
        <Header></Header>

        <h2>Home page</h2>

        <p>This is todo app using Vue.js, http request and Vue routing</p>

        <router-link to="/todos">Todo page</router-link>
    </div>
</template>

<script>
import Header from "@/components/layout/Header";

export default {
    components: {
        Header
    }
}
</script>

<style scoped>
    .home-page {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }

    h2 {
        margin-top: 50px;
    }

    p {
        margin-top: 30px;
    }
</style>
