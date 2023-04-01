<template>
  <section id="about" class="flex flex-col md:flex-row text-white h-screen">
    <div class="w-full md:w-1/2 px-5 md:pl-28 flex flex-col justify-center">
      <h2 class="text-left font-bold mb-4 textTitle text-6xl">Sobre mi</h2>
      <p class="text-left mb-4 formLetra">
        Soy Alec, cantante y compositor cubano. He estado trabajando duro para
        construir mi base de fans.
      </p>
      <p class="text-left mb-4 formLetra">
        Comencé publicando mi música en redes sociales como YouTube y Facebook.
        Luego comencé a recibir solicitudes de fans de todo el mundo para que
        mis canciones se publicaran en otras plataformas. Si te interersa y
        quieres saber lo que hago solo hecha un vistazo a la derecha.
      </p>
      <p class="text-left mb-4 formLetra">
        Si te interersa y quieres saber lo que hago solo hecha un vistazo a la
        derecha.
      </p>
    </div>
    <div class="w-full md:w-1/2 flex justify-center items-center p-5 md:p-20">
      <div
        style="height: 400px"
        class="
          w-full
          rounded-full
          bg-primary-opaco-dark
          flex
          justify-center
          items-center
          z-10
        "
      >
        <div class="flex flex-col space-x-2 px-10">
          <div>
            <h3 class="generosFont text-3xl ml-4">Géneros</h3>
          </div>

          <div class="flex flex-row flex-wrap">
            <div
              v-for="(chip, index) in chips"
              :key="index"
              class="
                w-24
                bg-pink-900
                px-5
                py-1
                m-1
                rounded-lg
                flex
                justify-center
                cursor-pointer
              "
            >
              <p>{{ chip }}</p>
            </div>
          </div>
        </div>
      </div>

      <img
        class="absolute z-0 right-12"
        src="../../static/Vectormusic2(1).svg"
        alt=""
      />
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      chips: ["Balada", "Pop", "Dancehall", "Urbano"],
    };
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&family=Simonetta&display=swap");
.generosFont {
  font-family: "Simonetta", cursive;
  font-weight: 100;
}

.formLetra {
  font-family: "Cookie", cursive;
  font-family: "PT Sans Caption", sans-serif;
}
.textTitle {
  font-family: "Cookie", cursive;
}

.tamaño {
  height: 400px;
  width: 400px;
}
.midTamaño {
  height: 500px;
  width: 500px;
}
.maxTamaño {
  height: 700px;
  width: 700px;
}
</style>
