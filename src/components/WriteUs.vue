<template>
  <div class="wrapper ma-5">
    <div class="text-center text-h6 mt-5 font-weight-bold">Напишите нам</div>
    <v-text-field
      label="Main input"
      :rules="rules"
      hide-details="auto"
      class="mx-16"
    ></v-text-field>
    <v-text-field label="Another input"
      :rules="rules"
      hide-details="auto" class="mx-16"></v-text-field>
  </div>
</template>

<script>
  export default {
    name: 'WriteUs',
    data: () => ({
      rules: [
        (value) => !!value || 'Required.',
        (value) => (value && value.length >= 3) || 'Min 3 characters',
      ],
    }),
  };
</script>

<style scoped>
  .wrapper {
    background: linear-gradient(
      180deg,
      rgba(224, 223, 255, 0.8) 0%,
      rgba(236, 236, 255, 0.5) 100%
    );
    width: 50%;
  }
</style>
