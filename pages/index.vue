<script>
import Main from "../components/main/Main.vue";
import Button from "../components/reusable/Button.vue";
export default {
  created() {
    this.$colorMode.value = "dark";
  },
  scrollToTop: true,
  components: { Main, Button },
};
</script>

<template>
  <!-- GO TO LAYOUTS/DEFAULT TO SEE THE CONTENT OF THE PAGE -->
  <div class="container mx-auto">
    <Main />
  </div>
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

* {
  font-family: "PT Sans Caption", sans-serif;
}
</style>
