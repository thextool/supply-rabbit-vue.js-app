<template>
 <div class='font'>
      <h5>{{school_name}}</h5>
      <h6>{{teachers_name}}</h6>
      <p>{{subtitled}}</p>
      <ul>
        <li v-for="item in items" :key="item.id">{{item}}</li>
      </ul>
       <router-link to="thankyou">DONATE</router-link>
    </div>
</template>

<script>

export default {
name: "DonationCheckout",
data(){
  return{
    school_name: 'Union Station School',
    teachers_name:'Anna Simmons',
    subtitled: 'Items',
    supply_name:['pencils','Notebooks','markers']
  }
}

};
</script>

<style>
.font{
  margin-top: 15%;
  color: #ffffff;
}
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
background-size: cover;
height: 100%;
}
</style>