<script>
import axios from "axios";
export default {
  data() {
    return {
      archetypes: [],
    };
  },
  methods: {
    fetchOption() {
      axios
        .get("https://db.ygoprodeck.com/api/v7/archetypes.php")
        .then((response) => {
          console.log(response.data);
          this.archetypes = response.data;
        });
    },
  },

  created() {
    this.fetchOption();
  },
};
</script>

<template>
  <section class="cards-container">
    <div class="container mb-2">
      <select class="form-select" aria-label="Default select example">
        <option selected>Open this select menu</option>

        <option v-for="archetipo in archetypes" value="1">
          {{ archetipo.archetype_name }}
        </option>
        <!-- <option value="2">Two</option>
        <option value="3">Three</option> -->
      </select>
    </div>
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
