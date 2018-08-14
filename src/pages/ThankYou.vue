<template>
<div class="font">
  <h1>Thank You</h1>
  <p>Send donation to NAME OF THE SCHOOL</P>
  <router-link to='donations'>DONATE MORE</router-link>
  <router-link to='/'>HOME</router-link>    
</div>
</template>

<script>

export default {
name: "ThankYou",
};
</script>

<style>
.font{
  margin-top: 10%;
  color: #ffffff;
}
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
background-size: cover;
height: 100%;
}
</style>
