<template>
  <div class="prices">
    <PriceTierIntro />
    <PriceTierList />
  </div>
</template>

<script>
import PriceTierIntro from '~/components/PriceTierIntro.vue';
import PriceTierList from '~/components/PriceTierList.vue';

export default {
  components: {
    PriceTierIntro,
    PriceTierList,
  },
  head() {
    return {
      title: 'Commission Prices',
    };
  },
};
</script>
