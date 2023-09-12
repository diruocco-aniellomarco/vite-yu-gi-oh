<script>
import AppCard from "./AppCard.vue";

export default {
  components: { AppCard },
};
</script>

<template>
  <section class="cards-container">
    <div class="container mb-2">
      <select class="form-select" aria-label="Default select example">
        <option selected>Open this select menu</option>
        <option value="1">One</option>
        <option value="2">Two</option>
        <option value="3">Three</option>
      </select>
    </div>
    <AppCard />
  </section>
</template>

<style lang="scss" scoped>
.cards-container {
  padding: 20px;
  background-color: orange;

  .form-select {
    width: 300px;
  }
}
.button-choise {
  background-color: white;
}
</style>
