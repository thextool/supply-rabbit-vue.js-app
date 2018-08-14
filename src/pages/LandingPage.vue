<template>
<div>
    <div id="Main"><h1>Brochure</h1></div>
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
}
h1 {
color: white;
}
#Main {
    border: 5px solid white;
    position: absolute;
    height: 20vw;
    width: 40vw;
    left: 30vw;
    top: 20vw;
}
</style>
