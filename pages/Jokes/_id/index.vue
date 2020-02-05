<template>
  <div>
    <div class="row">
      <h2>{{ joke }}</h2>
    </div>
    <div class="row">
      <nuxt-link to="/jokes" class="btn btn-primary">Back To Jokes</nuxt-link>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      joke: []
    };
  },

  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res = await axios.get(
        `https://icanhazdadjoke.com/j/${this.$route.params.id}`,
        config
      );

      this.joke = res.data.joke;
    } catch (error) {
      console.log(error);
    }
  },

  head() {
    return {
      title: this.$route.params.id
    };
  }
};
</script>