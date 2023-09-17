<script>
import axios from "axios";
import AppCard from "./AppCard.vue";
import AppCardSearch from "./AppCardSearch.vue";
import AppSearch from "./AppSearch.vue";
export default {
  data() {
    return {
      selected: "",
      cards: [],
      view: true,
    };
  },
  components: { AppCard, AppSearch, AppCardSearch },

  methods: {
    fetchSearch(selected) {
      this.view = false;

      axios
        .get(
          "https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype=" + selected
        )
        .then((response) => {
          this.cards = response.data.data;
          console.log(response.data.data);

          return this.cards;
        });
    },
  },
};
</script>

<template>
  <section class="cards-container">
    <AppSearch @start-search="fetchSearch" />
    <div class="container">
      <div v-if="cards.length > 0" class="found-cards col-12">
        Sono state trovate {{ cards.length }}
      </div>
      <div class="row">
        <AppCard v-if="view" />
        <AppCardSearch v-else :cards="cards" />
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.cards-container {
  padding: 20px;
  background-color: orange;
}

.container {
  background-color: white;
  padding-top: 25px;
  padding-bottom: 25px;
}

.found-cards {
  width: 100%;
  color: white;
  padding: 20px;
  background-color: #212529;
}
</style>
