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
  <div class="container">
    <!-- <div class="found-cards col-12">Found 20 cards</div> -->
    <div class="row">
      <div v-for="(card, index) in cards" class="card-container">
        <div class="d-flex flex-column text-center mb-2">
          <img :src="card.card_images[0].image_url_small" alt="" />
          <div class="card-text">
            <p class="text-light fw-bold">{{ card.name }}</p>

            <!-- Ho aggiunto un v-if perché nell'array non sempre è definito un archetipo della carta -->
            <p v-if="card.archetype">{{ card.archetype }}</p>
            <!-- Nota personale .text-light classe per testo bianco  -->
            <p v-else class="text-danger">- UNDEFINED ARCHETYPE -</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.found-cards {
  width: 100%;
  color: white;
  padding: 20px;
  background-color: #212529;
}
.container {
  background-color: white;
  padding-top: 25px;
  padding-bottom: 25px;
}

.card-container {
  width: calc(100% / 5);
}
.card-text {
  background-color: orange;
}
</style>
