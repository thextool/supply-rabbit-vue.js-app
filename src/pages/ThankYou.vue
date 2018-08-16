<template>
<div class="font">
  <h1>Thank You</h1>
  <p>Thank you for your donation, please send supplies to {{teacherAddress}}</p>
  <router-link to='donations' @click='deleteRequest'>DONATE MORE</router-link>
  <router-link to='/' @click='deleteRequest'>HOME</router-link>
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
},
methods:{
  deleteRequest(){
  let params = window.location.href.split('=')[1]
    fetch(`https://supply-rabbit-server.herokuapp.com/supplies/${params}`,{
      method:'DELETE',
      headers:{
      'Content-Type': 'application/json'
    }})
    .then(response => response.json)
    .then(response => console.log(response))
  }
}
}
</script>

<style>
.font{
  margin-top: 10%;
  color: #ffffff;
}
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.75), rgba(0, 0, 0, 0.75)),
    url("https://cbsla.files.wordpress.com/2015/09/shutterstock_200876306.jpg");
background-size: cover;
height: 100%;
}
</style>
