<template>
  <div>
    <div class="row">
      <Search v-on:search-text="sendSearchRequest" />
    </div>
    <div class="row">
      <Joke v-for="joke in jokes" :key="joke.id" :id="joke.id" :joke="joke.joke" />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Joke from "../../components/Joke";
import Search from "../../components/Search";

export default {
  components: {
    Joke,
    Search
  },

  data() {
    return {
      jokes: []
    };
  },

  async created() {
    const config = {
      headers: {
        Accept: "application/json"
      }
    };

    try {
      const res = await axios.get("https://icanhazdadjoke.com/search", config);

      this.jokes = res.data.results;
    } catch (error) {
      console.log(error);
    }
  },

  methods: {
    async sendSearchRequest(text) {
      const config = {
        headers: {
          Accept: "application/json"
        }
      };

      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        );

        this.jokes = res.data.results;
      } catch (error) {
        console.log(error);
      }
    }
  },

  head() {
    return {
      title: "Jokes"
    };
  }
};
</script>