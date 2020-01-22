<template>
  <div class="price-tier-list">
    <v-dialog
      v-model="dialog"
      fullscreen
      transition="fade-transition"
    >
      <v-card
        @click="dialog = false"
        :ripple="false"
        tile
        dark
        align="center"
      >
        <v-img
          :src="dialogSrc"
          contain
          style="height:100vh;"
        />
        <div class="dialog-close">
          <v-icon x-large>
            mdi-close
          </v-icon>
        </div>
      </v-card>
    </v-dialog>

    <v-container>
      <v-row
        class="text-center white--text"
      >
        <v-col
          cols="12"
        >
          <h1 class="my-12">
            ●COMMISSION PRICES●
          </h1>
          <p class="custom-style-4">
            All listed prices are subject to increase depending on Character Complexity.<br>
            Simple backgrounds are
            <span class="color-highlight-green">included</span>
            in all commission types.
          </p>
        </v-col>
      </v-row>

      <v-row>
        <v-col
          v-for="tier in tierList"
          :key="tier.id"
          cols="12"
          md="12"
        >
          <v-card
            dark
            class="text-center pa-4"
            color="#444"
          >
            <h2>
              <span>{{ tier.category }}</span>
            </h2>

            <p>
              <span style="white-space: pre-wrap;">{{ tier.price }}</span>
            </p>

            <p v-if="tier.description">
              <span style="white-space: pre-wrap;">{{ tier.description }}</span>
            </p>

            <p v-if="tier.alert" class="tier-alert">
              <span style="white-space: pre-wrap;">{{ tier.alert }}</span>
            </p>

            <v-row class="px-2" align="center">
              <v-col
                v-for="example in tier.examples"
                :key="example.id"
                cols="4"
              >
                <v-card
                  hover
                  outlined
                >
                  <v-img
                    :src="example.src"
                    @click="openDialog(example)"
                    max-height="400px"
                    contain
                  />
                </v-card>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import tierList from '../data/tier-list.json';

export default {
  name: 'PriceTierList',
  data: () => ({
    count: 0,
    dialog: false,
    dialogSrc: '',
    tierList,
  }),
  methods: {
    openDialog(example) {
      this.dialogSrc = example.src;
      this.dialog = true;
    },
  },
};
</script>

<style scoped>
  .price-tier-list {
    background-color: #222;
  }

  .tier-title {
    font-size: 1.5em;
  }

  .tier-alert {
    color: #ef5454;
    text-shadow: 0 0 8px;
  }

  .color-highlight-green {
    color: rgb(78, 154, 8);
  }

  .dialog-close {
    position:fixed;
    top:0;
    right:0;
    padding: 2rem;
    color:white;
    text-shadow: 0 0 2px black;
  }
</style>
