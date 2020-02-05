<template>
  <nuxt-link :to="'jokes/' + id">
    <div>
      <p>{{ joke }}</p>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: "Joke",
  props: ["joke", "id"]
};
</script>