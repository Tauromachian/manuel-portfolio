<script>
import AppBanner from "../components/shared/AppBanner.vue";
import Button from "../components/reusable/Button.vue";
export default {
  created() {
    this.$colorMode.value = "dark";
  },
  scrollToTop: true,
  components: { AppBanner, Button },
};
</script>

<template>
  <!-- GO TO LAYOUTS/DEFAULT TO SEE THE CONTENT OF THE PAGE -->
  <div class="container mx-auto">
    <AppBanner />
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

* {
  font-family: "PT Sans Caption", sans-serif;
}
</style>
