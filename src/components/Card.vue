<template>
<router-link to='checkout'>
  <div id= 'card' class='donations-card'>
      <h5>{{school_name}}</h5>
      <h6>{{teachers_name}}</h6>
      <p>Items</p>
      <ul >
       <li v-for="item in supply_name" :key="item.id" class="font">{{item}}</li>
      </ul>

    </div>
    </router-link>
    
</template>

<script>

export default {
name: 'Card',
data(){
  return{
    school_name: 'Union Station School',
    teachers_name:'Anna Simmons',
    subtitled: 'Items',
    supply_name:['pencils','Notebooks','markers', 'colored paper']
  } 
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