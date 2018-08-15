<template>
 <div class='font'>
      <h3 class="mdc-typography--headline3">{{school_name}}</h3>
      <h4 class="mdc-typography--headline4">{{teachers_name}}</h4>
      <h6 class="mdc-typography--headline6">{{subtitled}}</h6>
      <ul>
        <li v-for="item in supply_name" :key="item.id">{{item}}</li>
      </ul>
       <router-link to="thankyou" class="button">DONATE</router-link>
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
ul{
  list-style-type: none;
}
.button{
  background: #ffffff;
  padding: 5px;
  color: #000000;
}
body {
  margin: 0;
  padding: 0;
  background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
  background-size: cover;
  height: 100%;
  text-align: center;

}
</style>