<template>
<div>
    <div id="Main">
        <h1>You Make A Difference.</h1>
        <h2>We Make It Easier.</h2>
        </div>
    <router-view/>
</div>
</template>

<script>
export default {
name: "LandingPage",
};
</script>

<style>
#Main h1 {
color: white;
font-size: 3em;
        text-shadow: 5px 4px 0px rgba(255, 255, 255, 0.25), 4px 3px 0px rgba(0, 0, 0, 0.75);
}
#Main h2 {
    font-size: 2em;
            text-shadow: 4px 3px 0px rgba(255, 255, 255, 0.15), 3px 2px 0px rgba(0, 0, 0, 0.55);
}
#Main {
    color: white;
    display: flex;
    flex-direction: column;
    margin: 20vw;
}
</style>
