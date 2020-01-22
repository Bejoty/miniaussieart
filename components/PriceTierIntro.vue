<template>
  <v-img src="/good-morn_orig.jpg" min-height="100vh">
    <div class="intro py-6">
      <div>
        <MAALogo />

        <div class="sub-head">
          Digital Artist <br> Character Designer <br> Concept Artist <br> Animator
        </div>
      </div>

      <div class="social-links">
        <div
          v-for="(test, i) in links"
          :key="i"
        >
          <v-btn
            :href="test.url"
            :icon="$vuetify.breakpoint.xsOnly"
            class="my-3"
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
        </div>
      </div>
    </div>
  </v-img>
</template>

<script>
import links from '../data/links';
import MAALogo from './MAALogo';

export default {
  name: 'PriceTierIntro',
  components: {
    MAALogo,
  },
  data: () => ({
    links,
    socialVisible: true,
  }),
};
</script>

<style scoped>
  .intro {
    display: grid;
    height: 100%;
    align-content: space-around;
    text-align: center;
    background-image: linear-gradient(rgba(34, 34, 34, 0.1), rgba(34, 34, 34, 0.1) 80%, rgba(34, 34, 34, 1));
  }

  .sub-head {
    font-size: 1.5rem;
    font-weight: bold;
    text-shadow: 0 0 2px black;
  }

  .social-links {
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
  }

  @media(min-width: 600px) {
    .social-links {
      flex-direction: column;
    }
  }
</style>
