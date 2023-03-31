<script>
import { mapState } from "vuex";
import Navigation from "./HeaderNavigation.vue";

export default {
  components: {
    Navigation,
  },
  data: () => {
    return {
      isOpen: false,
      modal: false,
    };
  },

  computed: {
    ...mapState(["categories"]),
  },
  methods: {
    themeSwitcher() {
      this.$colorMode.preference =
        this.$colorMode.value == "light" ? "dark" : "light";
    },
    showModal() {
      if (this.modal) {
        // Stop screen scrolling
        document
          .getElementsByTagName("html")[0]
          .classList.remove("overflow-y-hidden");
        this.modal = false;
      } else {
        document
          .getElementsByTagName("html")[0]
          .classList.add("overflow-y-hidden");
        this.modal = true;
      }
    },
  },
};
</script>

<template>
  <nav style="" id="nav" class="sm:container sm:mx-auto z-10 float-right">
    <div
      style="background: linear-gradient(black, rgba(255, 255, 255, 0))"
      class="w-screen h-28 absolute top-0 left-0"
    ></div>
    <!-- Header -->
    <div
      class="
        z-10
        max-w-screen-lg
        xl:max-w-screen-xl
        block
        sm:flex sm:justify-between sm:items-center
        py-6
      "
    >
      <!-- Header menu links and small screen hamburger menu -->
      <div class="flex justify-between items-center px-6 sm:px-0">
        <!-- Small screen hamburger menu -->
        <div class="sm:hidden z-10">
          <button
            @click="isOpen = !isOpen"
            type="button"
            class="focus:outline-none"
            aria-label="Hamburger Menu"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              class="h-7 w-7 mt-1 fill-current text-ternary-light"
            >
              <path
                v-if="isOpen"
                fill-rule="evenodd"
                d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1 1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1 1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828 4.829 4.828 4.828z"
                clip-rule="evenodd"
              ></path>
              <path
                v-if="!isOpen"
                fill-rule="evenodd"
                d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
              ></path>
            </svg>
          </button>
        </div>
      </div>

      <!-- Header links -->

      <!-- Header right section buttons -->
      <div
        class="
          hidden
          sm:flex
          z-10
          justify-between
          items-center
          flex-col
          md:flex-row
        "
      >
        <Navigation
          :isOpen="isOpen"
          :showModal="showModal"
          :modal="modal"
          :categories="categories"
        />
        <!-- Hire me button -->
        <!--   <div class="font-general-medium hidden md:block">
          <button
            class="
              text-md
              bg-indigo-500
              hover:bg-indigo-600
              text-white
              shadow-sm
              rounded-md
              px-5
              py-2.5
            "
            @click="showModal()"
            aria-label="Hire Me Button"
          >
            Hire Me
          </button>
        </div>
 -->
      </div>
    </div>

    <!-- Header logos -->
    <div
      class="
        mt-56
        md:mt-0 md:pr-44
        w-full
        z-10
        flex
        justify-center
        items-center
      "
    >
      <p class="alecText text-8xl text-white">Alec</p>
    </div>
  </nav>
</template>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

.alecText {
  font-family: "Cookie", cursive;
}
</style>
