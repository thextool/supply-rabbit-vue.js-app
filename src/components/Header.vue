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
        background: rgba(0, 0, 0, 0.50);
        color: white;
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        margin-bottom: 10%;
    }
    #Header h1:active {
        transition: 0.4s;
        color: cadetblue;
        
    }
    #Header h1 {
        transition: 0.4s;
        margin-left: 2vw;
        text-shadow: 5px 4px 0px rgba(255, 255, 255, 0.25), 4px 3px 0px rgba(0, 0, 0, 0.75);
    }
    nav {
        margin-right: 2vw;
    }
    nav a {
        transition: 0.2s;
        font-size: 0.8em;
        text-transform: uppercase;
        text-decoration: none;
        border: 2px solid white;
        padding: 0.5vw;
        margin: 0.5vw;
        color: white;
    }
    nav a:hover {
        transition: 0.2s;
        background-color: white;
        color: black;
        box-shadow:  inset 0 0 0 3px  white;
    }
    nav a:active {
        background-color: rgba(0, 0, 0, 0);
        box-shadow: none;
        border-style: hidden;
        color: white;
    }
    a {
        text-decoration: none;
    }
</style>
