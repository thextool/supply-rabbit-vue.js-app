<template>
    <div id="Header">
        <h1 class="mdc-typography--headline3">Supply Rabbit</h1>
        <nav>
            <a href="#">Teachers</a>
            <a href="#">Donors</a>
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
    }
    nav a {
        border: 1px solid black;
        padding: 5px;
        color: white;
    }
</style>
