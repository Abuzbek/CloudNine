<template>
  <v-app>
    <Navbar :title="navItem" />
    <Header />
    <Skill />
    <div class="infoSection">
      <WriteUs class="writeUs" />
      <Map class="map" />
    </div>
  </v-app>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Header from './components/Header.vue';
import Skill from './components/Skill.vue';
import WriteUs from './components/WriteUs';
import Map from './components/Map';
// import TeamMemberCard from './components/TeamMemberCard';

export default {
  name: 'App',
  components: {
    // TeamMemberCard,
    Map,
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

  .infoSection {
    display: flex;
    flex-wrap: nowrap;
    margin-bottom: 10%;
  }

  .writeUs {
    width: 40%;
  }

  .map {
    width: 60%;
  }


  /*  =======================  components  ===============  */
  body {
    font-family: 'Montserrat', sans-serif;
  }
</style>
