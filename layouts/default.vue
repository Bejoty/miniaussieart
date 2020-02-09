<template>
  <v-app dark>
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<style>
  /* TODO - Figure out why Nuxt/Vue/Vuetify isn't loading global SASS (where this style is defined) */
  .overflow-y-hidden {
    overflow-y: hidden;
  }
</style>
