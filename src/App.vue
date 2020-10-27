<template>
  <v-app>
    <Navbar :title="navItem" />
    <Header />
    <Skill />
    <WriteUs />
  </v-app>
</template>

<script>
  import Navbar from './components/Navbar.vue';
  import Header from './components/Header.vue';
  import Skill from './components/Skill.vue';
  import WriteUs from './components/WriteUs';

  export default {
    name: 'App',
    components: {
      Navbar,
      Header,
      Skill,
      WriteUs,
    },
    data: () => ({
      //
    }),
  };
</script>

<style>
  /*  =======================  components  ===============  */
  .navbar-collapse {
    flex-basis: 0% !important;
  }
  .navbar-nav {
    flex-direction: row !important;
  }
  .nav-link {
    display: block;
    padding: 0.5rem 1rem !important;
    color: #2a2a2a;
  }
  .nav-link.active {
    font-weight: 700;
  }
  /*  =======================  components  ===============  */
  body {
    font-family: 'Montserrat', sans-serif;
  }
</style>
