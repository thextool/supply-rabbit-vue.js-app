<template>
<div class='cards-container'>
    
    <Card/>
    <Card/>
    <Card/>
    <Card/>


</div>
</template>

<script>
import Card from "../components/Card";
export default {
name: "Donations",
components:{
    Card:Card,
    
}
};
</script>

<style>
.cards-container{
    
    margin: 10%;
    display: flex;
    flex-wrap: wrap;

    
    
}
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
background-size: cover;
height: 100%;
}
</style>
