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
  <div class="container mx-auto">
    <AppBanner />

    <!-- View more projects button -->
    <div class="mt-5 z-10 sm:mt-14 flex justify-center"></div>
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

* {
  font-family: "PT Sans Caption", sans-serif;
}
</style>
