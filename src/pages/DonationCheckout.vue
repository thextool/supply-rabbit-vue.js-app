<template>
  <div class='font' style="background-color:white; color: black; ">
    <div>Teacher: {{teacher.name}}</div>
    <h3 class="mdc-typography--headline3">{{donation.school}}</h3>
    <h4 class="mdc-typography--headline4">{{donation.name}}</h4>
    <h6 class="mdc-typography--headline6">Supplies</h6>
    <ul>
      <li>{{donation.supply_name}}</li>
    </ul>
    <button @click="goToThankYou" class="button">DONATE</button>
  </div>
</template>

<script>
export default {
  name: "DonationCheckout",
  data() {
    return {
      donation: {},
      teacher: {}
    };
  },
  created() {
    this.fetchDonation(this.$route.params.id).then(teacherId =>
      this.fetchTeacher(teacherId)
    );
  },
  methods: {
    fetchDonation(id) {
      return fetch(`https://supply-rabbit-server.herokuapp.com/supplies/${id}`)
        .then(response => response.json())
        .then(data => {
          this.donation = data.supplies;
          return data.supplies.id;
        });
    },
    fetchTeacher(id) {
      fetch(`https://supply-rabbit-server.herokuapp.com/teachers/${id}`)
        .then(response => response.json())
        .then(data => (this.teacher = data.teachers))
    },
    goToThankYou() {
      location.replace(`http://localhost:8080/#/thankyou=${this.$route.params.id}`)
    }
  }
};
</script>

<style>
.font {
  margin-top: 15%;
  color: #ffffff;
}
ul {
  list-style-type: none;
}
.button {
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