<template>
<router-link to='checkout'>
  <div id= 'card' class='donations-card'>
      <h3>School name</h3>
      <h4>Teacher</h4>
      <div class='donation-items'>
        <p>Items</p>
        <ul>
          <li>Item1</li>
          <li>Item2</li>
          <li>Item3</li>
        </ul>
      </div>
    </div>
    </router-link>
    
</template>

<script>

export default {
name: 'Card'
};
</script>

<style>
li{
  list-style-position: inside;
}
ul {
  display: flex;
  flex-flow: column wrap;
  align-items: flex-start;
}
.donations-items {
  display: flex;
  align-content: flex-start;
}
p {
  color: red;
}
.font{
  color: #000000;
}
.donations-card {
  background: #ffffff;
  height: 250px;
  width: 250px;
}
</style>