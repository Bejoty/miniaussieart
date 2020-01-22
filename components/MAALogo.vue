<template>
  <h1
    :class="{'logo-resize': $vuetify.breakpoint.smAndUp}"
    class="my-4 font-weight-bold text-uppercase logo color-logo"
  >
    <span>Mi<span class="logo-shrink-letter">n</span>iAussie</span><span class="color-logo-red">A</span><span class="color-logo-green">r</span><span class="color-logo-blue">t</span>
  </h1>
</template>

<script>
export default {
  name: 'MAALogo',
};
</script>

<style scoped>
  .logo {
    font-size: 2.4rem;
    font-family: 'Architects Daughter', sans-serif;
    text-shadow: 0 0 3px black;
  }

  @media(min-width: 400px) {
    .logo {
      font-size: 3.4rem;
    }
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
</style>
