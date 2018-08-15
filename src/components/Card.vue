<template>
 <router-link to='checkout'> 
  <div id= 'card' class='donations-card'>
    
      <h5>{{result}}
      <!-- <h6>{{}}</h6>
      <p>Items</p>
      <ul >
       <li v-for="item in supply_name" :key="item.id" class="font">{{item}}</li>
      </ul> --> 

    </div>
    </router-link>
    
</template>

<script>

export default {
name: 'Card',
data(){
  return{
  methods:{
    populateCards(){
      const API_URL = 'https://supply-rabbit-server.herokuapp.com/supplies;'
      fetch(API_URL)
      .then(res=>res.json())
      .then(result=>{
        console.log(data)
          })
        }
      }
    };
  }       
};
</script>

<style>

.font{
  color: #000000;
}
.donations-card {
  background: #ffffff;
  height: 350px;
  width: 350px;
  margin: 16px;
  
}
</style>