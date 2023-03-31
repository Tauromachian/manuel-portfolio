<template>
  <div class="bg-primary-dark min-h-screen w-full flex flex-col">
    <!-- App header -->
    <Header />

    <!-- Render contents with transition -->
    <transition name="fade" mode="out-in">
      <Nuxt />
    </transition>

    <AboutMe></AboutMe>
    <MostRecent></MostRecent>
    <!-- App footer -->
    <Contact />

    <!-- Go back to top when scrolled down -->
    <div
      class="
        flex
        space-x-2
        mr-8
        mb-6
        right-0
        bottom-0
        z-50
        fixed
        items-center
        sm:space-x-4
      "
    >
      <BackToTop />
    </div>
  </div>
</template>

<script>
import feather from "feather-icons";
import Header from "../components/header/Header.vue";
import Contact from "../components/contact/Contact.vue";
import BackToTop from "../components/BackToTop.vue";
import MostRecent from "../components/mostRecent/MostRecent.vue";
import AboutMe from "../components/about/AboutMe.vue";
export default {
  data: () => {
    return {
      // Todo
    };
  },
  mounted() {
    this.$colorMode.value = "dark";
    feather.replace();
  },
  components: { MostRecent, Contact, BackToTop, Header, AboutMe },
};
</script>

<style>
.vue-back-to-top {
  @apply p-2 sm:p-4 bg-indigo-500 hover:bg-indigo-600 text-white;
  border-radius: 50%;
  font-size: 22px;
  line-height: 22px;
}

.fade-enter-active {
  animation: coming 0.4s;
  animation-delay: 0.2s;
  opacity: 0;
}

.fade-leave-active {
  animation: going 0.4s;
}

@keyframes going {
  from {
    transform: translateX(0);
  }

  to {
    transform: translateX(-10px);
    opacity: 0;
  }
}

@keyframes coming {
  from {
    transform: translateX(-10px);
    opacity: 0;
  }

  to {
    transform: translateX(0px);
    opacity: 1;
  }
}
</style>
