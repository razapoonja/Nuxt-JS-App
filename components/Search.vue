<template>
  <form @submit.prevent="searchJoke">
    <input class="form-control" type="text" v-model="text" placeholder="Search Jokes..." />
  </form>
</template>

<script>
export default {
  name: "Search",
  data() {
    return {
      text: ""
    };
  },
  methods: {
    searchJoke() {
      this.$emit("search-text", this.text);
      this.text = "";
    }
  }
};
</script>