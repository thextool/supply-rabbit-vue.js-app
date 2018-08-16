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

    h1{
        margin-left: 20px;
    }
    nav a {
        border: 2px solid white;
        padding: 10px;
        margin: 5px;
        margin-right: 20px;
        color: white;
    }

    nav a:hover {
        background-color: white;
        color: black;
        box-shadow:  inset 0 0 0 3px  white;
    }
</style>
