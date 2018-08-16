<template>
    <div id="Header">
        <router-link to="/"><h1>Supply Rabbit</h1></router-link>
        <nav>
            <router-link to="/teachers">Teachers</router-link>
            <router-link to="/donations">Donations</router-link>
        </nav>
    </div>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style>
    #Header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        border-bottom: 2px solid black;
        background: black;
        color: white;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        margin-bottom: 10%;
    }
    nav a {
        border: 1px solid white;
        padding: 5px;
        color: white;
    }
</style>
