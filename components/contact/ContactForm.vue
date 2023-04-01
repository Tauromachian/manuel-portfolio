<script>
import Button from "../reusable/Button.vue";
export default {
  components: { Button },
  data: () => {
    return {
      // @todo
    };
  },
};
</script>

<template>
  <!-- Contact form -->
  <div class="w-full max-w-xl md:w-2/3 flex justify-center items-center">
    <div class="absolute right-0 z-0">
      <img class="object-contain w-2/3 h-auto" src="/claveSol.svg" alt="" />
    </div>
    <div
      class="
        w-full
        leading-loose
        max-w-xl
        m-4
        z-10
        p-7
        bg-primary-opaco-dark
        rounded-xl
        shadow-xl
        text-left
      "
    >
      <form
        @submit="
          (e) => {
            e.preventDefault;
          }
        "
        class="formLetra space-y-7"
      >
        <div class="">
          <label class="block text-lg text-primary-light mb-2" for="name"
            >Nombre</label
          >
          <input
            class="
              w-full
              px-5
              py-2
              border border-primary-dark border-opacity-50
              text-primary-light
              bg-primary-opaco-cleandark
              rounded-md
              shadow-sm
              text-md
            "
            id="name"
            name="name"
            type="text"
            required=""
            placeholder="Tu Nombre"
            aria-label="Nombre"
          />
        </div>
        <div class="mt-6">
          <label class="block text-lg text-primary-light mb-2" for="email"
            >Correo</label
          >
          <input
            class="
              w-full
              px-5
              py-2
              border border-primary-dark border-opacity-50
              text-primary-light
              bg-primary-opaco-cleandark
              rounded-md
              shadow-sm
              text-md
            "
            id="email"
            name="email"
            type="text"
            required=""
            placeholder="tu@email.tu"
            aria-label="Email"
          />
        </div>

        <div class="mt-6">
          <label class="block text-lg text-primary-light mb-2" for="message"
            >Mensaje</label
          >
          <textarea
            class="
              w-full
              px-5
              py-2
              border border-primary-dark border-opacity-50
              text-primary-light
              bg-primary-opaco-cleandark
              rounded-md
              shadow-sm
              text-md
            "
            id="message"
            name="message"
            cols="14"
            rows="6"
            placeholder="Dime lo que quieras"
            aria-label="Message"
          ></textarea>
        </div>

        <div class="mt-6">
          <Button
            title="Enviar Mensaje"
            class="
              float-right
              px-4
              py-2.5
              text-white
              tracking-wider
              bg-primary-red
              hover:bg-red-400
              focus:ring-1 focus:ring-indigo-900
              rounded-lg
              duration-500
            "
            type="submit"
            aria-label="Enviar Mensaje"
          />
        </div>
      </form>
    </div>
  </div>
</template>
<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

.formLetra {
  font-family: "Cookie", cursive;
  font-family: "PT Sans Caption", sans-serif;
}
</style>
