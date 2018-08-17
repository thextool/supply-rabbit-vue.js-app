<template>
  <div class="margin-top">
    <!-- <h5 class="mdc-typography--headline5 font-color">School: {{donation.school}}</h5> -->
    <h5 class="mdc-typography--headline5 font-color">Teacher: {{teacher.name}}</h5>
    <h5 class="mdc-typography--headline5 font-color text-underline">Supplies Needed</h5>
    <p class="mdc-typography--headline4 font-color">{{donation.name}}</p>
    <ul class="mdc-list">
      <li class='class="mdc-list-item" mdc-typography--body1 font-color'>{{donation.supply_name}} x {{donation.quantity_needed}}</li>
    </ul>
    <button @click="goToThankYou" class="button mdc-typography--button text-decoration">DONATE</button>
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
      location.replace(`https://supply-rabbit-96c3e.firebaseapp.com/#/thankyou=${this.$route.params.id}`)
    }
  }
};
</script>

<style>
.margin-top{
  margin-top: 15%;
}
.font-color {
  color: #ffffff;
}
.text-decoration{
  text-decoration: none;
}
.content{
  display: flex;
  flex-direction: column;
  justify-content: start;
  align-items: start;
}

ul {
  list-style-type: none;
}
.button {
  background: #ffffff;
  padding: 5px;
  color: #000000;
  border-radius: 5px;
}
body {
  margin: 0;
  padding: 0;
}
</style>
