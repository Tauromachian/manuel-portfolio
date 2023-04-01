<template>
  <section id="recent ">
    <div class="pl-5 mt-56 md:mt-0 md:pl-28 text-white">
      <h3 class="text-6xl textTitle">Lo más reciente</h3>
      <ul class="flex">
        <li
          class="
            p-5
            rounded-lg
            cursor-pointer
            transition-colors
            duration-300
            hover:bg-gray-200 hover:bg-opacity-25
          "
          :style="content == 'canciones' ? selected : {}"
          @click="content = 'canciones'"
        >
          Música
        </li>
        <li
          class="
            rounded-lg
            p-5
            cursor-pointer
            transition-colors
            duration-300
            hover:bg-gray-200 hover:bg-opacity-25
          "
          :style="content == 'videos' ? selected : {}"
          @click="content = 'videos'"
        >
          Videos
        </li>
        <li
          class="
            rounded-lg
            p-5
            cursor-pointer
            transition-colors
            duration-300
            hover:bg-gray-200 hover:bg-opacity-25
          "
          :style="content == 'fotos' ? selected : {}"
          @click="content = 'fotos'"
        >
          Fotos
        </li>
      </ul>
    </div>
    <SongList v-if="content == 'canciones'" />
    <VideoList v-if="content == 'videos'" />
    <FotoList v-if="content == 'fotos'" />
  </section>
</template>

<script>
import SongList from "./songList.vue";
import VideoList from "./videoList.vue";
import FotoList from "./fotoList.vue";
export default {
  data() {
    return {
      content: "canciones",
      selected: { borderBottom: "solid 1px red" },
    };
  },
  components: {
    SongList,
    VideoList,
    FotoList,
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Cookie&family=PT+Sans+Caption&display=swap");

.textTitle {
  font-family: "Cookie", cursive;
}
</style>
