<script>
import feather from "feather-icons";

export default {
  data: () => {
    return {
      // Todo
    };
  },

  mounted() {
    feather.replace();
  },
  updated() {
    feather.replace();
  },
};
</script>

<template>
  <section
    class="
      flex flex-col
      h-screen
      md:justify-between
      items-center
      md:flex-row
      mt-12
      md:mt-10
    "
  >
    <!-- Music Note 2Corchea -->
    <img class="absolute top-0 left-0" src="~/static/music-note.svg" alt="" />

    <!-- Banner right illustration -->
    <div
      style="width: auto; min-width: min-content"
      class="
        w-full
        absolute
        h-full
        md:w-1/2 md:left-1/2
        top-0
        z-0
        right-0
        flex
        justify-end
      "
    >
      <img
        class="
          w-screen
          filter
          brightness-50
          md:brightness-100
          h-full
          object-cover
          rounded-b-3xl
          md:rounded-br-none
          mt-6
        "
        src="~/static/alecPicture.png"
        alt="Alec Picture"
      />
    </div>
    <!-- Banner left contents -->
    <div class="w-full md:w-1/3 md:mb-52 text-left z-10">
      <h1
        class="
          font-general-semibold
          text-3xl
          md:text-3xl
          xl:text-4xl
          text-center
          sm:text-left
          text-ternary-light
          uppercase
        "
      >
        Hola!
      </h1>
      <p
        class="
          font-general-medium
          mt-2
          text-lg
          sm:text-xl
          xl:text-2xl
          text-center
          sm:text-left
          leading-none
          text-white
        "
      >
        Mi nombre es Alec. Un placer tenerte aca!!
      </p>
      <div class="flex justify-center sm:block">
        <a
          download=""
          class="
            flex
            justify-center
            items-center
            w-36
            sm:w-48
            mt-12
            mb-6
            sm:mb-0
            cursor-pointer
            text-lg
            border-ternary-dark
            py-2.5
            sm:py-3
            shadow-lg
            rounded-lg
            bg-primary-red
            hover:bg-red-400
            focus:ring-1 focus:ring-indigo-900
            text-white
            hover:text-white
            duration-500
          "
        >
          <span class="text-sm sm:text-lg font-general-medium duration-100"
            >Contáctame</span
          ></a
        >
      </div>
    </div>
  </section>
</template>

<style></style>
