<template>
  <div id="app">
    <navbar/>
    <router-view/>
    <loginModal/>
    <fixedfooter/>
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Footer from "./components/Footer.vue";
import loginModal from "./components/loginModal.vue";

export default {
  data(){
    return{
      activeTab: null
    }
  },
  components: {
    navbar: Navbar,
    fixedfooter: Footer,
    loginModal: loginModal,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#app section{
  padding: 5px !important;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
