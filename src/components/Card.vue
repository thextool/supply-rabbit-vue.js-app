<template>
  <router-link :to="`checkout/${donation.id}`" class="text-decoration font"> 
    <div id='card' class='donations-card'>
      <h5 class="mdc-typography--headline5 ">{{donation.school}}</h5>
      <h6 class="mdc-typography--subtitle1">{{donation.name}}</h6>
      <h5 class="mdc-typography--headline5 text-underline">Items</h5>
      <ul class="mdc-list">
        <li class="mdc-list-item text-decoration">{{ donation.supply_name }}</li>
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
.text-decoration{
  text-decoration: none;
}
.text-underline{
  text-decoration:underline;
}
.donations-card {
  background: #ffffff;
  height: 300px;
  width: 300px;
  margin: 16px;
  padding: 3%;
  border-radius: 5px;
}

</style>