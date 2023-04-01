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
        <video
          :src="currentVideo"
          alt="Canción"
          class="w-96 h-96 object-cover rounded-md mb-8 shadow-lg"
          ref="videoPlayer"
        >
          Tu navegador no soporta la etiqueta video.
        </video>

        <div class="flex justify-start rounded-lg p-4 pl-0">
          <img
            src="../../static/assets/play.png"
            class="
              p-3
              cursor-pointer
              transition-colors
              rounded-lg
              duration-300
              hover:bg-gray-200 hover:bg-opacity-25
            "
            alt=""
            @click="playVideo()"
          />

          <img
            src="../../static/assets/pause.png"
            class="
              p-3
              rounded-lg
              cursor-pointer
              transition-colors
              duration-300
              hover:bg-gray-200 hover:bg-opacity-25
            "
            alt=""
            @click="pauseVideo()"
          />
        </div>

        <audio
          ref="audio"
          id="audio"
          :src="currentVideo"
          preload="auto"
        ></audio>
      </div>
      <!-- Columna de la lista de canciones -->
      <div
        class="w-full bg-primary-opaco-dark rounded-lg text-white md:w-1/2 p-8"
      >
        <h2 class="text-3xl font-bold mb-4 title">Videos</h2>
        <div style="height: 500px; overflow-y: scroll">
          <ul>
            <li
              v-for="(video, index) in videoList"
              :key="index"
              class="
                flex
                items-center
                mb-4
                cursor-pointer
                transition-colors
                duration-300
                hover:bg-gray-200 hover:bg-opacity-25
              "
              @click="changeVideo(video)"
            >
              <img :src="video.img" class="w-12 h-12 rounded mr-4" />
              <span class="itemList">{{ video.name }}</span>
            </li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoList",

  data() {
    return {
      currentVideo: null,
      currentImg: null,
      videoList: [
        {
          img: "/music/img/EuropeCarrie.jpg",
          src: "/video/lovefool.mp4",
          name: "Postmodern Jukebox - Lovefool",
        },
        {
          img: "/music/img/TotoAfrica.jpg",
          src: "/video/creep.mp4",
          name: "Postmodern Jukebox - Creep",
        },
        {
          img: "/music/img/TotoAfrica.jpg",
          src: "/video/thunderstruck.mp4",
          name: "2Chellos - Thunderstruck",
        },
      ],
      audio: null,
    };
  },
  mounted() {
    this.video = this.$refs.videoPlayer;
    this.currentVideo = this.videoList[0].src;
    this.currentImg = this.videoList[0].img;
  },

  methods: {
    playVideo() {
      this.video.play();
    },
    pauseVideo() {
      this.video.pause();
    },
    async changeVideo(video) {
      this.currentVideo = video.src;
      this.currentImg = video.img;
      this.video.src = this.currentVideo;
      await this.video.load();
      this.video.play();
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
