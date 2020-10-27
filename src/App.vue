<template>
  <v-app>
    <WriteUs />
  </v-app>
</template>

<script>
  import WriteUs from './components/WriteUs';

  export default {
    name: 'App',

    components: {
      WriteUs,
    },

    data: () => ({
      //
    }),
  };
</script>
