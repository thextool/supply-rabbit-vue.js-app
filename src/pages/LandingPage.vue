<template>
<div>
    <Header />
    <div id="Main"><h1>Main</h1></div>
    <Footer />
</div>
</template>

<script>
import Header from "../components/Header";
import Footer from "../components/Footer";
export default {
name: "LandingPage",
components: {
    Header: Header,
    Footer: Footer
}
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
</style>
