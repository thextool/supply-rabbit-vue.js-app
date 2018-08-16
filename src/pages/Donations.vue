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
  justify-content: center;
  flex-wrap: wrap;
  overflow: scroll;
}
</style>
