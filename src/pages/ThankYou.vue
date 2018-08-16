<template>
<div class="font" id="ThankYou">
  <h1>Thank You</h1>
  <p>Thank you for your donation, please send supplies to {{teacherAddress}}</p>
  <router-link to='donations'>DONATE MORE</router-link>
  <router-link to='/'>HOME</router-link>
  <div>
    <GoogleMap/>
  </div>   
</div>
</template>

<script>
import GoogleMap from "../components/GoogleMap"

export default {
name: "ThankYou",
components:{
    GoogleMap
},
data() {
  return {
  params: window.location.href.split('=')[1],
  teacherAddress: ""
  }
},
created() {
  let params = window.location.href.split('=')[1]
  fetch(`https://supply-rabbit-server.herokuapp.com/teachers/${params}`)
  .then(response => response.json())
  .then(teachers => this.teacherAddress = teachers.teachers.address)
}
};
</script>

<style>
.font{
  margin-top: 10%;
  color: #ffffff;
}
#ThankYou h1 {
    font-size: 2.5em;
}
#ThankYou p {
  margin: 2em;
}
#ThankYou a {
  transition: 0.2s;
  font-size: 0.8em;
  text-transform: uppercase;
  text-decoration: none;
  border: 2px solid white;
  padding: 10px;
  margin: 1em;
  color: white;
}
#ThankYou a:hover {
  transition: 0.2s;
  background-color: white;
  color: black;
  box-shadow:  inset 0 0 0 3px  white;
}
#ThankYou a:active {
  background-color: rgba(0, 0, 0, 0);
  box-shadow: none;
  border-style: hidden;
  color: white;
}
</style>
