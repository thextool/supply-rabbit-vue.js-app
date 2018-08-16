<template>
  <router-link :to="`checkout/${donation.id}`"> 
    <div id='card' class='donations-card'>
      <h5 class="mdc-typography--headline4">{{donation.school}}</h5>
      <h6 class="mdc-typography--headline6">{{donation.name}}</h6>
      <p>Items</p>
      <ul>
        <li>{{ donation.supply_name }}</li>
      </ul> 
    </div>
  </router-link>    
</template>

<script>
export default {
  name: "Card",
  props: ['donation']
};
</script>

<style>
.font {
  color: #000000;
}
.donations-card {
  background: #ffffff;
  height: 350px;
  width: 350px;
  margin: 16px;
}
</style>