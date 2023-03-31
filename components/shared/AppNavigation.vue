<script>
export default {
  props: ["isOpen", "showModal", "modal", "categories"],
};
</script>

<template>
  <!-- App header navigation links -->
  <div
    :class="isOpen ? 'block' : 'hidden'"
    class="
      font-general-regular
      m-0
      sm:ml-4
      mt-5
      sm:mt-3 sm:flex
      p-5
      sm:p-0
      z-10
      justify-center
      items-center
      shadow-lg
      sm:shadow-none
    "
  >
    <h3
      class="
        rounded-lg
        p-5
        cursor-pointer
        transition-colors
        duration-300
        hover:bg-gray-200 hover:bg-opacity-25
        block
        text-left text-lg text-ternary-light
      "
      aria-label="Projects"
    >
      Sobre mi
    </h3>
    <h3
      class="
        rounded-lg
        cursor-pointer
        transition-colors
        duration-300
        p-5
        hover:bg-gray-200 hover:bg-opacity-25
        block
        text-left text-lg text-ternary-light
        hover:text-secondary-light hover:
        border-t-2
        sm:border-t-0
        border-primary-light
      "
      aria-label="About Me"
    >
      Lo más reciente
    </h3>
    <h3
      class="
        rounded-lg
        cursor-pointer
        transition-colors
        duration-300
        p-5
        hover:bg-gray-200 hover:bg-opacity-25
        block
        text-left text-lg text-ternary-light
        hover:text-secondary-light hover:
        border-t-2
        sm:border-t-0
        border-secondary-light
      "
      aria-label="Contact"
    >
      Contáctame
    </h3>
  </div>
</template>

<style>
#nav .nuxt-link-exact-active,
#nav .nuxt-link-active {
  @apply text-indigo-700 text-indigo-400;
}
</style>
