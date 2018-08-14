<template>
 <div class='font'>
      <h5>School name</h5>
      <h6>Teacher</h6>
      <p>Items</p>
      <ul>
        <li>Item1</li>
        <li>Item2</li>
        <li>Item3</li>
      </ul>
       <router-link to="thankyou">DONATE</router-link>
    </div>
</template>

<script>

export default {
name: "DonationCheckout",

};
</script>

<style>
.font{
  color: #ffffff;
}
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
background-size: cover;
height: 100%;
}
</style>