<template>
<router-link to='checkout'>
  <div id= 'card' class='donations-card'>
      <h5>School name</h5>
      <h6>Teacher</h6>
      <p>Items</p>
      <ul>
        <li>Item1</li>
        <li>Item2</li>
        <li>Item3</li>
      </ul>

    </div>
    </router-link>
    
</template>

<script>

export default {
name: 'Card'
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
}
</style>