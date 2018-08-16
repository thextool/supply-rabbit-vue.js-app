

<template>
    <div id="Footer">
    <small>&copy; 2018 Supply Rabbit - All Rights Reserved</small>
    </div>
</template>

<script>
export default {
    name: 'Footer'
}
</script>

<style>
#Footer {
    display: flex;
    justify-content: center;
    align-items: center;
    border-top: 2px solid black;
    position: fixed;
    bottom: 0;
    height: 10%;
    width: 100%;
    left: 0;
    background: rgba(0, 0, 0, 0.5);
    color: white;
}

</style>
