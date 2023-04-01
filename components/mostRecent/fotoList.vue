<template>
  <div class="px-4 md:px-24">
    <div class="flex flex-col md:flex-row w-full h-3/6">
      <!-- Columna del reproductor de video y botones -->
      <div
        class="
          w-full
          md:w-1/2
          flex flex-col
          justify-center
          items-center
          px-8
          pt-8
          rounded-lg
        "
      >
        <img
          :src="currentFoto"
          alt="Canción"
          class="w-96 h-96 object-cover rounded-md mb-8 shadow-lg"
        />
      </div>
      <!-- Columna de la lista de canciones -->
      <div
        class="w-full bg-primary-opaco-dark rounded-lg text-white md:w-1/2 p-8"
      >
        <h2 class="text-3xl font-bold mb-4 title">Fotos</h2>
        <div style="height: 500px; overflow-y: scroll" class="">
          <ul class="flex items-center justify-center flex-wrap">
            <li
              v-for="(foto, index) in fotoList"
              :key="index"
              class="
                flex
                items-center
                justify-center
                mb-4
                cursor-pointer
                transition-colors
                duration-300
              "
              @click="changeFoto(foto)"
            >
              <img :src="foto.src" class="w-24 h-24 rounded mr-4" />
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FotoList",

  data() {
    return {
      currentFoto: null,
      currentImg: null,
      fotoList: [
        {
          src: "/images/1.jpg",
        },
        {
          src: "/images/2.jpg",
        },
        {
          src: "/images/3.jpg",
        },
        {
          src: "/images/4.jpg",
        },
        {
          src: "/images/5.jpg",
        },
        {
          src: "/images/1.jpg",
        },
        {
          src: "/images/2.jpg",
        },
        {
          src: "/images/3.jpg",
        },
        {
          src: "/images/4.jpg",
        },
        {
          src: "/images/5.jpg",
        },
      ],
      audio: null,
    };
  },
  mounted() {
    this.currentFoto = this.fotoList[0].src;
  },

  methods: {
    async changeFoto(foto) {
      this.currentFoto = foto.src;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&family=Simonetta&display=swap");
.title {
  font-family: "Simonetta", cursive;
  font-weight: 100;
}
.itemList {
  font-family: "PT Sans Caption", sans-serif;
}
</style>
