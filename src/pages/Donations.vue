<template>
<div class='cards-container'>
    <Card
        v-for="donation in donations" 
        v-bind:key="donation.id"
        v-bind:donation="donation"
    />
</div>
</template>

<script>
import Card from "../components/Card";
export default {
  name: "Donations",
  components: {
    Card: Card
  },
  data() {
    return {
      donations: []
    };
  },
  created() {
    fetch("https://supply-rabbit-server.herokuapp.com/supplies")
      .then(response => response.json())
      .then(data => (this.donations = data.supplies));
  }
};
</script>

<style>
.cards-container {
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
