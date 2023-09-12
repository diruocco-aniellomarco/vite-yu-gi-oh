<script>
import axios from "axios";
export default {
  data() {
    return {
      title: "ciao",
      cards: [],
    };
  },
  methods: {
    fetchCards() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0")
        .then((response) => {
          console.log(response.data.data);
          this.cards = response.data.data;
        });
    },
  },

  created() {
    this.fetchCards();
  },
};
</script>

<template>
  <section class="container">
    <div class="row">
      <div v-for="(card, index) in cards" class="col-3">
        <div class="d-flex flex-column text-center">
          <img :src="card.card_images[0].image_url_small" alt="" />

          <p>{{ card.name }}</p>

          <!-- Ho aggiunto un v-if perché nell'array non sempre è definito un archetipo della carta -->
          <p v-if="card.archetype">{{ card.archetype }}</p>
          <!-- Nota personale .text-light classe per testo bianco  -->
          <p v-else class="text-danger">- UNDEFINED ARCHETYPE -</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped></style>
