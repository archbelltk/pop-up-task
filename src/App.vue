<template>
  <div>
    <button v-on:click="openPopup">View</button>
    <RandomPost ref="randomPost" />
  </div>
</template>

<script>
import RandomPost from "./components/RandomPost.vue";

export default {
  components: {
    RandomPost
  },
  methods: {
    openPopup() {
      this.$refs.randomPost.openPopup();
    }
  }
};
</script>

<style>
#app {
  text-align: center;
  margin-top: 20px;
}
</style>
