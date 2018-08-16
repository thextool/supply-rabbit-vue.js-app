<template>
  <div id="app">
    <Header />
    <router-view/>
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header';
import Footer from './components/Footer';
export default {
  name: 'App',
  components: {
    Header,
    Footer
  }
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
body {
background-image: linear-gradient(rgba(0, 0, 0, 0.60), rgba(0, 0, 0, 0.0)),
    /* url("https://cdn.pixabay.com/photo/2016/09/26/09/58/school-supplies-1695563_1280.jpg"); */
    url("https://www.maxpixel.net/static/photo/2x/Plastic-Painting-School-Supplies-Color-Tempera-1695564.jpg");
background-size: 100%;
background-repeat: no-repeat;
background-attachment: fixed;
height: 100%;
/* overflow: hidden; */
}
h1 {
color: white;
}
</style>

