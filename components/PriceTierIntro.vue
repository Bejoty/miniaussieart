<template>
  <v-container fluid class="intro fill-height text-center">
    <v-row class="mx-auto" justify="center">
      <v-col
        col="12"
        md="8"
        lg="6"
      >
        <h1
          :class="{'logo-resize': $vuetify.breakpoint.smAndUp}"
          class="my-4 font-weight-bold text-uppercase logo color-logo"
        >
          <span>Mi<span class="logo-shrink-letter">n</span>iAussie</span><span class="color-logo-red">A</span><span class="color-logo-green">r</span><span class="color-logo-blue">t</span>
        </h1>
        <div class="sub-head">
          Digital Artist <br> Character Designer <br> Concept Artist <br> Animator
        </div>
      </v-col>
    </v-row>

    <v-row class="mx-auto" justify="center">
      <v-col
        cols="12"
        md="8"
      >
        <v-row>
          <v-col
            v-for="(test, i) in links"
            :key="i"
            xs="4"
            sm="12"
          >
            <v-btn
              :href="test.url"
              :icon="$vuetify.breakpoint.xsOnly"
              target="_blank"
              dark
              x-large
              style="background-color: rgba(0, 0, 0, 0.5);"
            >
              <v-icon>
                {{ test.icon }}
              </v-icon>
              <span class="ml-3 d-none d-sm-flex">{{ test.text }}</span>
            </v-btn>
          </v-col>
        </v-row>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import links from '../data/links';

export default {
  name: 'PriceTierIntro',
  data: () => ({
    links,
    socialVisible: true,
  }),
};
</script>

<style scoped>
  @import url('https://fonts.googleapis.com/css?family=Architects+Daughter&display=swap');

  .logo {
    font-size: 2.4rem;
    font-family: 'Architects Daughter', sans-serif;
    text-shadow: 0 0 3px black;
  }

  .logo-resize {
    font-size: 3.4rem;
  }

  .logo-shrink-letter {
    font-size: 0.85em;
  }

  .color-logo {
    color: #50c0cd;
  }

  .color-logo-red {
    color: #ef5454;
  }

  .color-logo-blue {
    color: #4fb7e7;
  }

  .color-logo-green {
    color: #9bd33a;
  }

  .sub-head {
    font-size: 1.5rem;
    font-weight: bold;
    text-shadow: 0 0 2px black;
  }

  .intro {
    background-image: linear-gradient(rgba(34, 34, 34, 0.1), rgba(34, 34, 34, 0.1) 80%, rgba(34, 34, 34, 1));
  }
</style>
