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
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
background-size: cover;
height: 100%;
/* overflow: hidden; */
}
h1 {
color: white;
}
#Main {
    color: white;
    display: flex;
    flex-direction: column;
    margin: 20vw;
}
</style>
