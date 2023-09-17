<script>
import AppCard from "./AppCard.vue";
import AppSearch from "./AppSearch.vue";
export default {
  components: { AppCard, AppSearch },
};
</script>

<template>
  <section class="cards-container">
    <AppSearch />
    <AppCard />
  </section>
</template>

<style lang="scss" scoped>
.cards-container {
  padding: 20px;
  background-color: orange;
}
</style>
